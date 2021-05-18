Financial Health Pulse - Transactional Data Methodology Overview
================

*Updated: May 2021*

This document provides an in-depth explanation of the methodology used
to collect and analyze transactional data in the Financial Health Pulse.
If you have any questions or would like to discuss further, please
contact us at: <pulse@finhealthnetwork.org>.

## I. Pulse Overview

The [Financial Health
Pulse](https://finhealthnetwork.org/score/score-methodology/) is a
rigorous, widely publicized, and regularly refreshed snapshot of
financial health. Leveraging the[FinHealth
Score®](https://finhealthnetwork.org/score/score-methodology/)
measurement methodology, longitudinal consumer surveys, and
transactional data, the Pulse provides a regularly refreshed snapshot of
the country’s financial health and how it is changing over time.

Survey data are collected through the University of Southern
California’s [“Understanding America
Study,”](https://uasdata.usc.edu/index.php) (UAS) a nationally
representative probability-based internet panel. The surveys employ a
cross-sectional and longitudinal design, allowing researchers to explore
how financial health changes for the country and for individual
respondents over time.

Transactional data are collected from study participants who consent to
link their financial accounts to a secure online platform that leverages
[Plaid’s](https://plaid.com/build-with-plaid/?utm_source=google&utm_medium=search&utm_campaign=Search_G_Brand_Exact&utm_content=Com&utm_term=plaid&utm_creative=442292869083&gclid=EAIaIQobChMI7-Xjw9uO7AIVEL7ACh3-LwYLEAAYASAAEgLQofD_BwE)
API. These data allow researchers to track key elements of consumers’
financial lives and disaggregate trends by demographics, socioeconomic
characteristics, and survey responses.

## II. Data Collection

As of May, 2021, 918 participants had linked at least one financial
account, out of a total of 8,797 invited panelists, yielding a
participation rate of 10.4%. Participants linked 5,854 accounts across
2,534 financial institutions; the mean number of accounts linked by
participants was 6.4 and the median was 4. An additional 26 individuals
linked accounts that never provided information via the Plaid linkage.
We exclude those people from our analysis and reporting.

**Participation Eligibility**

Financial Health Network and USC’s Center for Economic and Social
Research have sent several waves of consent surveys to UAS panelists on
an ongoing basis. Since the Pulse data-sharing platform only allows
users to connect accounts that are online or mobile-accessible,
individuals who do not bank online or via a mobile device are not
eligible to participate in the study. To determine eligibility, UAS
panelists received a consent survey asking them whether they had used
mobile and/or online banking in the past 12 months. If respondents said
that they banked online or used a mobile device, they were invited to
link their financial accounts (such as checking accounts, savings
accounts, credit cards, mortgages, 401(k)s, student loans, etc.) to a
secure online platform that leverages Plaid’s API.

**Linking Accounts**

To link accounts, participants logged onto the platform using a unique
URL and followed interactive instructions to provide their credentials
for online financial accounts they owned. Respondents were provided
information about the secure storage of their financial information and
instructions about how they could unlink their accounts. Participants
receive an initial $10 incentive for every institution they link to the
platform and a $1 incentive for each month the institution remains
actively linked to the platform.

**User Experience**

The following images display screens that participants see as the link
accounts.

*Image 1. Landing page for participation in transactional data
collection*

<img src="https://github.com/financialhealthnetwork/pulse-txnl-analysis/blob/staging/Reports/markdown1.png" width="500" />

*Image 2.Initial account linkage page for a checking account*

<img src="https://github.com/financialhealthnetwork/pulse-txnl-analysis/blob/staging/Reports/markdown2.png" width="500" />

*Image 3. Prompt for linking less common accounts*

<img src="https://github.com/financialhealthnetwork/pulse-txnl-analysis/blob/staging/Reports/markdown3.png" width="500" />

**Data Security**

Given the sensitive nature of transactional data, the USC research team
cleans the data set and removes data fields that could potentially
contain personally identifiable information (including vendor id,
transaction description, and institution name) prior to sharing the
dataset with the Financial Health Network. Thus, the data set used for
analysis includes Plaid’s transaction categorizations, information on
the account used, the transaction dollar amount, the running balance in
accounts, and the date of transaction. The Financial Health Network does
not have access to participants’ credentials (e.g. username or
password). We also take additional precautions to ensure that the data
are stored securely and with minimal risk of re-identification through
use of Amazon Web Services S3 buckets and structured credentials for the
analytical team at the Financial Health Network. All members of the
analytical team complete IRB Human Subjects research training.

## III. Data Set Construction

Participants linked a wide variety of account types, with checking
accounts, savings accounts, and credit cards linked most frequently.

#### **Table 1. Sample Sizes by Linked Account Type as of May 2021 (Before Applying Inclusion Criteria)**

| Account Type                                                                           | Number of individuals with Linked Accounts | Average Balance, EOD ($) |
| :------------------------------------------------------------------------------------- | -----------------------------------------: | -----------------------: |
| Checking Account                                                                       |                                        851 |                  1050.85 |
| Savings Account                                                                        |                                        609 |                   703.75 |
| Credit Card                                                                            |                                        539 |                  6771.90 |
| Any Loan                                                                               |                                        282 |                  3332.23 |
| Brokerage/Investment Account (401k, IRAs, and other retirement or investment accounts) |                                        196 |                  9492.53 |
| Other                                                                                  |                                        188 |                     3.11 |
| Money Market Account                                                                   |                                         33 |                  5489.01 |
| Cash Management                                                                        |                                         12 |                   977.18 |
| Prepaid                                                                                |                                          9 |                     3.71 |

**Comparisons to account ownership as indicated in survey data**

We compared account ownership reported by transactional data collection
participants on a Pulse survey (fielded between April 20 and May 7,
2020) to the actual accounts linked in order to assess the consistency
of the account data in the two sources (see table below). We found
fairly high consistency for checking accounts, savings accounts, and
credit cards, indicating that the financial accounts linked by
participants were generally the same as those that they reported owning
in the Pulse survey. The high degrees of consistency for these accounts,
and lower amounts of consistency for other types of financial accounts,
helped us make the decision to focus our analysis solely on credit cards
and liquid accounts.

|                                                                                                                      | % of study participants who reported owning account on survey who linked the account to the data sharing platform |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------: |
| Checking                                                                                                             |                                                                                                              0.93 |
| Credit.card                                                                                                          |                                                                                                              0.71 |
| Saving                                                                                                               |                                                                                                              0.80 |
| Employer.provided.retirement.account..such.as.a.401k..403.b..or.Thrift.Savings.Plan..TSP…etc..                       |                                                                                                              0.16 |
| Prepaid.card                                                                                                         |                                                                                                              0.01 |
| Individual.retirement.account.not.provided.by.an.employer..such.as.an.IRA..Keogh..SEP..or.any.other.retirement.fund. |                                                                                                              0.28 |
| Cash.management..money.market..health.savings.account..HAS…and.or.certificate.of.deposit..CD.                        |                                                                                                              0.24 |
| Brokerage.account..annuity..profit.sharing.stock.plan..and.or.529.plan                                               |                                                                                                              0.36 |
| Employer.provided.traditional.pension.or.cash.balance.plan                                                           |                                                                                                              0.02 |
| Other.financial.assets.or.accounts                                                                                   |                                                                                                              0.22 |
|                                                                                                                      |                                                                                                                   |

There are several potential explanations for the observed differences
between reported account ownership on the Pulse survey and the rate at
which these accounts were actually linked:

  - Participants did not have online accounts for transactional accounts
    they reported owning on the survey
  - Participants did not have ready access to online credentials for
    transactional accounts they reported owning on the survey
  - Less-frequently used transactional accounts did not come to mind for
    respondents during the Pulse transactional data linkage process
  - There were technical issues in the account-linking platform

**Inclusion Criteria**

In order to construct the transactional data set used for analysis, we
developed and applied filtering criteria to the collected data. We also
applied additional definitions and inclusion thresholds for certain
metrics, such as minimum account activity thresholds (see the metric
definitions table for complete information).

To be included in the Pulse transactional data set, a financial account
must be actively linked:

  - At the beginning of the study period
  - At the end of the study period
  - For 80% of the study period

Ensuring that accounts are actively linked via Plaid means we receive a
regular flow of data for that account and can therefore be confident in
the completeness of the data. When account linkages go inactive because
of changed account credentials or participants unlinking their accounts,
for example, the data flow stops and financial activity that occurs
during the period of inactivity may be missed.

We chose these inclusion criteria to ensure that we had sufficient data
on all individuals in the sample during the study period and to ensure
that there were no systematic time-based skews within the data (e.g.,
many individuals missing data at the beginning or end of the study
period). The sample sizes for all accounts dropped significantly after
applying our inclusion criteria, reflecting the amount of missing
account data in the data set. Checking accounts, savings accounts, and
credit cards remained the most common accounts in our data set after
applying the inclusion criteria.

**Sample Composition**

The overall demographic composition of the final Pulse transactional
data set broadly aligns with the demographic composition of individuals
who said they banked online or via a mobile device in the Financial
Health Pulse surveys. We use this sample as our benchmark because it
most closely aligns with the group of individuals who were eligible to
participate in the transactional data portion of the study, since the
Pulse data-sharing platform only captures information from online or
mobile-accessible financial accounts. As a result, we would not expect
to see individuals who do not have a bank account or who solely use cash
represented in the transactional data sample.

However, there are some differences between the two datasets. Compared
with the sampling frame, the Pulse sample skews slightly higher income,
younger, and less financially healthy. There are also skews in the Pulse
sample along gender (with women overrepresented), race and ethnicity
(with Black respondents underrepresented), and education (with those
with less education underrepresented). A multiple regression analysis
confirmed that these demographic differences remained even after
controlling for other demographic characteristics. Therefore, the
findings from this data set should be considered directional and
illustrative, but not necessarily representative, of individuals in the
United States who bank online or using a mobile device.

**Sub-Sample Composition**

Because we break the overall sample into smaller subsamples based on
account ownership for analysis, we also examined the demographics of
individuals who had linked a specific financial account. The demographic
composition of these subsamples differ slightly from that of Pulse
survey respondents who bank online or via a mobile device, but
differences remain fairly small and intuitive (for example, individuals
who linked a credit card have higher income and are more financially
healthy).

The tables below summarize the demographic compositions of individuals
in different transactional samples relative to the unweighted survey
sample of individuals who bank online or using a mobile device.

A small number of participants in our transactional data collection did
not respond to the Q2 Pulse survey, so we do not have demographic data
on a small proportion of the sample (indicated by the “NA” categories in
the tables below).

| Household Income  | Unweighted survey data (Q2 2020, online banked) | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
| :---------------- | ----------------------------------------------: | -------------------------------------: | -----------------------------: | -----------------: |
| Less than $30,000 |                                            0.15 |                                   0.16 |                           0.18 |               0.09 |
| $30,000 - $59,999 |                                            0.22 |                                   0.25 |                           0.22 |               0.21 |
| $60,000 - $99,999 |                                            0.29 |                                   0.26 |                           0.26 |               0.32 |
| $100,000 or more  |                                            0.34 |                                   0.33 |                           0.33 |               0.38 |

| Gender   | Unweighted survey data (Q2 2020, online banked) | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
| :------- | ----------------------------------------------: | -------------------------------------: | -----------------------------: | -----------------: |
| 0 Female |                                            0.57 |                                   0.59 |                           0.56 |               0.51 |
| 1 Male   |                                            0.43 |                                   0.41 |                           0.44 |               0.49 |

| Race/Ethnicity | Unweighted survey data (Q2 2020, online banked) | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
| :------------- | ----------------------------------------------: | -------------------------------------: | -----------------------------: | -----------------: |
| NLAsian        |                                            0.07 |                                   0.07 |                           0.09 |               0.11 |
| NLBlk          |                                            0.04 |                                   0.06 |                           0.07 |               0.02 |
| Latinx         |                                            0.13 |                                   0.18 |                           0.19 |               0.15 |
| NLWHT          |                                            0.71 |                                   0.66 |                           0.61 |               0.66 |
| NLOth          |                                            0.00 |                                   0.01 |                           0.00 |                 NA |
| NLMultiple     |                                            0.04 |                                   0.02 |                           0.03 |               0.05 |
| NA             |                                            0.00 |                                     NA |                           0.00 |                 NA |

| Education Level             | Unweighted survey data (Q2 2020, online banked) | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
| :-------------------------- | ----------------------------------------------: | -------------------------------------: | -----------------------------: | -----------------: |
| Less than high school       |                                            0.02 |                                   0.02 |                           0.03 |               0.01 |
| High school                 |                                            0.09 |                                   0.09 |                           0.10 |               0.07 |
| Some college                |                                            0.33 |                                   0.33 |                           0.35 |               0.30 |
| Bachelor’s degree or higher |                                            0.56 |                                   0.56 |                           0.53 |               0.62 |

| Age Group   | Unweighted survey data (Q2 2020, online banked) | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
| :---------- | ----------------------------------------------: | -------------------------------------: | -----------------------------: | -----------------: |
| 18-25       |                                            0.10 |                                   0.12 |                           0.12 |               0.12 |
| 26-35       |                                            0.23 |                                   0.24 |                           0.27 |               0.28 |
| 36-49       |                                            0.31 |                                   0.32 |                           0.30 |               0.32 |
| 50-64       |                                            0.23 |                                   0.20 |                           0.20 |               0.19 |
| 65 and over |                                            0.13 |                                   0.12 |                           0.11 |               0.10 |

| Currently Working | Unweighted survey data (Q2 2020, online banked) | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
| :---------------- | ----------------------------------------------: | -------------------------------------: | -----------------------------: | -----------------: |
| 0 No              |                                            0.32 |                                   0.33 |                           0.35 |               0.23 |
| 1 Yes             |                                            0.68 |                                   0.67 |                           0.65 |               0.77 |

| Financial Health Tier | Unweighted survey data (Q2 2020, online banked) | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
| :-------------------- | ----------------------------------------------: | -------------------------------------: | -----------------------------: | -----------------: |
| Healthy               |                                            0.35 |                                   0.29 |                           0.30 |               0.35 |
| Coping                |                                            0.56 |                                   0.54 |                           0.53 |               0.60 |
| Vulnerable            |                                            0.09 |                                   0.16 |                           0.15 |               0.03 |
| NA                    |                                            0.00 |                                   0.01 |                           0.02 |               0.01 |

## IV. Analytical Decisions

We apply several conventions in our analysis of the transactional
data.We typically make the following decisions when analyzing the data:

**Look-Back Period**

We use a 30-day look-back period when calculating all metrics. Given the
day-to-day noisiness of transactional data and the relative infrequency
of key financial events (e.g., the monthly cadence of many bills and the
relative uncommonness of late fees), we calculate a rolling look-back
period over the past 30 days because it strikes the right balance
between temporal accuracy and reduction of noise.

**Median Values**

When looking at dollar value figures in the transactional data set, we
typically report the median amount of a metric to avoid outliers
affecting the trends. For any given metric, we calculate the median
value for each day over the sample for whom the metric is calculated.
The table below summarizes the different account groupings we use for
analysis, sample sizes, and metric definitions.

**Activity Thresholds**

We apply basic transaction activity requirements for liquid account
inflows and outflows to ensure we are able to actually observe some
day-to-day transaction activity. We do not apply activity requirements
to other metrics, because transaction activity is less necessary in
those instances to calculate the metric (e.g., an individual can hold a
liquid account balance without having any transactions in the past 6
months).

**Transfers**

Transactions categorized as “transfers” are very common in our
transactional data; they constitute 19% of all outflow transactions and
30% of total transactions. Including transfers in the analysis of
inflows and outflows runs the risk of misidentifying transfers for the
purpose of moving funds between personal financial accounts as income or
an expenditure. We generally include transfers in our analysis because
we do not need to directly identify income and expenditures for our
metrics and because any potential double counting would be accounted for
in our analysis. Furthermore, excluding transfers could run the risk of
biasing subsequent analysis against individuals who own investment
accounts, brokerage accounts, or any other type of account where
transfers are common.

*Definitions of Metrics*

<img src="https://github.com/financialhealthnetwork/pulse-txnl-analysis/blob/staging/Reports/markdown8.PNG" width="1000" />

## V. Study Limitations

**Sample Size**

The total sample size of just over 800 participants in the Pulse
transactional data set limits our ability to examine smaller demographic
subsamples, particularly after we apply our inclusion criteria. We are
actively exploring ways to increase our sample size.

**Cash Usage**

Since the data-sharing platform only allows users to connect accounts
that are online or mobile-accessible, individuals who do not bank online
or via a mobile device are not eligible to participate in the study. We
are also not able to collect data on transactions conducted entirely in
cash; the most insight we can gain into cash usage using this data set
is examining ATM withdrawals or cash deposits into a linked account.
Therefore, we lack complete coverage of the financial transactions of
the unbanked, underbanked, and cash-preferred.

However, our relatively limited insight into cash usage should not
significantly impact our research findings. Research from the [Diary of
Consumer Payment Choice
research](https://www.frbatlanta.org/banking-and-payments/consumer-payments/diary-of-consumer-payment-choice/2019-diary.aspx)
indicates that cash transactions make up 6% of transactions by value and
26% of transactions by volume. Given our metrics focus on transaction
values and not transaction volume, this point of comparison suggests
that we are missing a relatively small amount of cash activity in our
Pulse transactional data set.

**Joint Accounts**

Participants are encouraged to link all of their transactional accounts.
It is possible that some of these accounts are held jointly by members
of a household and that multiple people conduct transactions using the
same account. Therefore, we may be observing transactions that are not
directly conducted by the research participant. We are currently unable
to ascertain which accounts are jointly held; therefore, we may
overestimate the number, size, and volume of transactions or savings for
particular accounts.
[Prior](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3404834/)
[research](https://onlinelibrary.wiley.com/doi/abs/10.1111/j.1741-3737.2003.00525.x)
shows that the majority of married couples hold joint financial
accounts, so this source of error may be heightened for individuals who
are married.

**Attrition**

The total number of linked accounts in our transactional data set has
gradually decreased after participants initially linked their accounts.
For example, 20% of all accounts linked had become inactive. This
attrition generally occurs when user credentials expire or change, or
users voluntarily delink their financial institutions, resulting in
inactive account links. Checking accounts, savings accounts, and credit
card accounts are most likely to attrite. We hypothesize that this is
because frequent use of these accounts prompts financial institutions to
force users to reset their password more frequently than for other
account types. When the user resets their password with their financial
institution, they likely do not also update it in the UAS Plaid
interface.

Our partners at USC send regular reminders to users whose accounts
become inactive to encourage them to relink their accounts. We also
offer participants a $5 incentive to relink accounts that have gone
inactive. However, in practice, very few participants have actively
relinked accounts. We continue to actively examine how to combat
attrition.

**Missing Data**

We are not able to access all transactional data from a given financial
account after a participant links that account. Although the Plaid API
allows us to see past transactions that go back a limited time period
after an account is linked, accounts are deemed “inactive” in those past
dates and balances cannot be observed.We use [Plaid’s “Assets”
product](https://plaid.com/docs/#assets) to capture historical account
balances at the time an individual linked an account, but attrition and
the limits of historical data collection mean we still face challenges
in working with missing data

**Seasonality**

The amount of historical data we are able to gather when an individual
links an account via Plaid limits our current ability to understand the
impact of seasonality on the transactional trends we observe in the
Pulse data set. The amount of time that we are able to look back into
someone’s transactions prior to their linking of an account varies by
account type and institution, though the modal length of time is about 6
months. Given the majority of our participants first linked their
account(s) in June 2020, we can only retrieve complete data going back
to January 2020 for the majority of the sample. As a result, we cannot
currently compare trends to previous years of data, and thus may lack
some context into which trends are driven by seasonal factors that might
be driving these trends. Furthermore, the unique economic context in
which we have started our data collection may make this period difficult
to use as a baseline for comparison for future data. Over time, though,
we will gather sufficient data to allow us to compare to previous years.

## VI. Looking Ahead

We will continue to analyze the collected transactional data over time.
We aim to improve the data quality and size of the sample over time,
making the transactional data and merged survey and transactional data
set even more valuable. We also intend to make the transactional data
set available for use by other researchers, in addition to our already
[publicly available survey
data](https://finhealthnetwork.org/programs-and-events/financial-health-pulse/data/).

Please direct any questions about the transactional data research to
<pulse@finhealthnetwork.org>.
