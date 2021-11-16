Financial Health Pulse - Transactional Data Methodology Overview
================

*Updated: November 2021*

This document provides an in-depth explanation of the methodology used
to collect and analyze transactional data in the Financial Health Pulse.
If you have any questions or would like to discuss further, please
contact us at: <pulse@finhealthnetwork.org>.

To see the 2020 Financial Health Pulse Trends Report Methodology
Supplement, visit [this
link](https://s3.amazonaws.com/cfsi-innovation-files-2018/wp-content/uploads/2018/10/07161756/2020-Pulse-Trends-Report-Methodology-Supplement-Oct-2020.pdf).

*Update:* As of 10/12/2021, the data in this document have been updated
to correct a filtering issue with the merged survey and transactional
data sets. The data have been filtered to show the most recent survey
responses of participants in our research.

## I. Pulse Overview

The [Financial Health
Pulse](https://finhealthnetwork.org/programs/financial-health-pulse/) is
a rigorous, widely publicized, and regularly refreshed snapshot of
financial health. Leveraging the [FinHealth
Score®](https://finhealthnetwork.org/tools/financial-health-score/)
measurement methodology, longitudinal consumer surveys, and
transactional data, the Pulse provides a regularly refreshed snapshot of
the country’s financial health and how it is changing over time.

Survey data are collected through the University of Southern California
Center for Economic and Social Research [“Understanding America
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

As of October 12, 2021, 979 participants had linked at least one
financial account to the Pulse platform, out of a total of 8,961
invitees (this does not account for people who have been invited more
than once), yielding a participation rate of 10.9%. Participants linked
6,151 accounts across 2,619 financial institutions; the mean number of
accounts linked by participants was 6 and the median was 4. Only
individuals who linked accounts and provided information via the plaid
linkage were included in this analysis and reporting.

**Participation Eligibility**

Since the Pulse data-sharing platform only allows users to connect
accounts that are online or mobile-accessible, individuals who do not
bank online or via a mobile device are not eligible to participate in
the study. To determine eligibility, the Financial Health Network and
USC send consent surveys to UAS panelists on an ongoing basis. These
consent surveys ask panelists whether they have used mobile and/or
online banking in the past 12 months. If respondents respond in the
affirmative, they are invited to link their financial accounts to a
secure online platform that leverages Plaid’s API.

**Linking Accounts**

To link accounts, participants log onto the Pulse platform using a
unique URL and follow interactive instructions to provide their
credentials for their online financial accounts. Respondents are
provided information about the secure storage of their financial
information and instructions about how they can unlink their accounts if
they wish. Participants receive an initial $10 incentive for every
institution they link to the platform and a $1 incentive for each month
the institution remains actively linked to the platform.

**User Experience**

The following images display screens that participants see as the link
accounts to the Pulse platform.

**Image 1. Landing page for participation in the study**

<img src="https://github.com/financialhealthnetwork/pulse-transactional-methodology-public-/blob/main/pic1.png" width="500" />

**Image 2.Initial account linkage page**

<img src="https://github.com/financialhealthnetwork/pulse-transactional-methodology-public-/blob/main/pic2.png" height="500" />

**Image 3. Prompt for linking less common accounts**

<img src="https://github.com/financialhealthnetwork/pulse-transactional-methodology-public-/blob/main/pic3.png" width="500" />

**Data Security**

Given the sensitive nature of transactional data, the USC research team
cleans the data set and removes data fields that could potentially
contain personally identifiable information (including vendor id,
transaction description, and institution name) prior to sharing the
dataset with the Financial Health Network. The data set used for
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

Participants have linked many types of accounts, with checking accounts,
savings accounts, and credit cards linked most frequently.

#### **Table 1. Sample Sizes and Average Balance by Linked Account Type (Before Data Cleaning)**

| Account Type                                                                           | Number of individuals with Linked Accounts | Average Balance, EOD ($) |
|:---------------------------------------------------------------------------------------|-------------------------------------------:|-------------------------:|
| Checking Account                                                                       |                                        911 |                  1081.29 |
| Savings Account                                                                        |                                        655 |                   697.20 |
| Credit Card                                                                            |                                        570 |                  6900.00 |
| Any Loan                                                                               |                                        295 |                  3218.44 |
| Brokerage/Investment Account (401k, IRAs, and other retirement or investment accounts) |                                        192 |                  9492.53 |
| Other                                                                                  |                                        190 |                     4.53 |
| Money Market Account                                                                   |                                         31 |                  4500.71 |
| Cash Management                                                                        |                                         13 |                   440.00 |
| Prepaid                                                                                |                                         10 |                     3.08 |

In order to assess the alignment between self-reported account ownership
and accounts linked on the Pulse platform, we compare survey results
from an April 2021 Pulse survey to the linked accounts (Table 2) . We
find fairly high consistency across the two data sources for checking
accounts, savings accounts, and credit cards, indicating that the
financial accounts linked by participants were generally the same as
those that they reported owning in the Pulse survey. The high degrees of
consistency for these accounts, and lower amounts of consistency for
other types of financial accounts, help us make the decision to focus
our analysis on liquid accounts and credit cards.

#### **Table 2. Comparisons to account ownership as indicated in survey data**

| Account Type                                                                                                         | % of Study Participants who Linked an Account |
|:---------------------------------------------------------------------------------------------------------------------|----------------------------------------------:|
| Checking                                                                                                             |                                          0.93 |
| Credit card                                                                                                          |                                          0.71 |
| Saving                                                                                                               |                                          0.79 |
| Employer-provided retirement account (such as a 401k, 403(b) or Thrift Savings Plan (TSP), etc.)                     |                                          0.16 |
| Prepaid card                                                                                                         |                                          0.01 |
| Individual retirement account not provided by an employer (such as an IRA, Keogh, SEP, or any other retirement fund) |                                          0.27 |
| Cash management, money market, health savings account (HSA), and/or certificate of deposit (CD)                      |                                          0.22 |
| Brokerage account, annuity, profit sharing/stock plan, and/or 529 plan                                               |                                          0.37 |
| Employer-provided traditional pension or cash balance plan                                                           |                                          0.02 |
| Other financial assets or accounts                                                                                   |                                          0.27 |
|                                                                                                                      |                                               |

There are several potential explanations for the observed differences
between reported account ownership on the Pulse survey and the rate at
which these accounts were actually linked:

-   Participants did not have online accounts for transactional accounts
    they reported owning on the survey
-   Participants did not have ready access to online credentials for
    transactional accounts they reported owning on the survey
-   Less-frequently used transactional accounts did not come to mind for
    respondents during the Pulse transactional data linkage process
-   There were technical issues in the account-linking platform

We continue to conduct research into the differences between survey
responses and participants’ linked accounts.

**Inclusion Criteria**

In order to construct the transactional data set typically used for
analysis, we apply cleaning criteria to the collected data. We also
apply additional definitions and inclusion thresholds for certain
metrics, such as minimum account activity thresholds (see Table 3 for
more).

To be included in the Pulse transactional data set, a financial account
must be actively linked:

-   At the beginning of the study period
-   At the end of the study period
-   For 80% of the study period

Ensuring that accounts are actively linked via Plaid means we receive a
regular flow of data for that account and can therefore be confident in
the completeness of the data. When account linkages go inactive because
of changed account credentials or participants unlinking their accounts,
for example, the data flow stops and financial activity that occurs
during the period of inactivity may be missed.

We choose these inclusion criteria to ensure that we have sufficient
data on all individuals in the sample during the study period and to
ensure that there are no systematic time-based skews within the data
(e.g., many individuals missing data at the beginning or end of the
study period). The sample sizes for all accounts drop significantly
after applying our inclusion criteria, reflecting the amount of missing
account data in the data set. Checking accounts, savings accounts, and
credit cards remain the most common accounts in our data set after
applying the inclusion criteria.

## IV. Sample Composition

The overall demographic composition of the cleaned Pulse transactional
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
with those in the Pulse survey who bank online or using mobile accounts,
the Pulse transactional sample skews slightly higher income, younger,
and less financially healthy. There are also skews along gender (with
women overrepresented), race and ethnicity (with Black respondents
underrepresented), and education (with those with less education
underrepresented). A multiple regression analysis confirmed that these
demographic differences remained even after controlling for other
demographic characteristics. Therefore, the findings from this data set
should be considered directional and illustrative, but not necessarily
representative of national or demographic trends in the United States.

Given our interest in sharing nationally representative insights, we
considered weighting the data set of transactions based on the
demographic characteristics of the respondents. Ultimately this approach
was abandoned for lack of a comparable nationally representative
benchmark (though the FDIC “How America Banks” CPS supplement was
considered) and because of the relatively small participant sample size
of the transactional data set. Additionally, because our inclusion
criteria for each metric created different subsamples of participants
that changed over time, weighting these subsamples for analysis on an
ongoing basis could have been impractical (see “metric construction” for
more information).

**Subsample Composition**

Because we break the overall sample into smaller subsamples based on
account ownership for analysis, we also examine the demographics of
individuals who linked particular financial accounts. The demographic
composition of these subsamples differs slightly from that of Pulse
survey respondents who bank online or via a mobile device, but
differences remain fairly small and intuitive (for example, individuals
who linked a credit card have higher income and are more financially
healthy than the other samples).

We typically use specific transactional data samples in our analysis.
The tables below summarize the demographic compositions of these samples
from the transactional data set relative to the unweighted Pulse survey
sample of individuals who bank online or using a mobile device.

A small number of participants in the transactional data sample did not
respond to Pulse surveys, so we do not have complete demographic data on
a small proportion of the sample (indicated by the “NA” categories in
the tables below).

| Household Income  | Online/mobile banked survey sample | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
|:------------------|-----------------------------------:|---------------------------------------:|-------------------------------:|-------------------:|
| Less than $30,000 |                               0.15 |                                   0.12 |                           0.14 |               0.05 |
| $30,000 - $59,999 |                               0.23 |                                   0.25 |                           0.22 |               0.20 |
| $60,000 - $99,999 |                               0.29 |                                   0.27 |                           0.25 |               0.33 |
| $100,000 or more  |                               0.33 |                                   0.32 |                           0.34 |               0.39 |
| NA                |                                 NA |                                   0.04 |                           0.05 |               0.03 |

| Gender | Online/mobile banked survey sample | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
|:-------|-----------------------------------:|---------------------------------------:|-------------------------------:|-------------------:|
| Female |                               0.59 |                                   0.57 |                           0.53 |               0.52 |
| Male   |                               0.41 |                                   0.40 |                           0.42 |               0.45 |
| NA     |                                 NA |                                   0.04 |                           0.05 |               0.03 |

| Race/Ethnicity | Online/mobile banked survey sample | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
|:---------------|-----------------------------------:|---------------------------------------:|-------------------------------:|-------------------:|
| Asian          |                               0.07 |                                   0.06 |                           0.09 |               0.09 |
| Black          |                               0.05 |                                   0.06 |                           0.06 |               0.03 |
| Latinx         |                               0.17 |                                   0.16 |                           0.17 |               0.17 |
| Multiple       |                               0.04 |                                   0.02 |                           0.03 |               0.05 |
| Other          |                               0.01 |                                   0.01 |                           0.01 |               0.01 |
| White          |                               0.66 |                                   0.65 |                           0.59 |               0.63 |
| NA             |                               0.00 |                                   0.04 |                           0.05 |               0.03 |

| Education Level             | Online/mobile banked survey sample | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
|:----------------------------|-----------------------------------:|---------------------------------------:|-------------------------------:|-------------------:|
| Less than high school       |                               0.02 |                                   0.03 |                           0.02 |               0.01 |
| High school                 |                               0.10 |                                   0.09 |                           0.09 |               0.09 |
| Some college                |                               0.35 |                                   0.32 |                           0.34 |               0.29 |
| Bachelor’s degree or higher |                               0.53 |                                   0.52 |                           0.50 |               0.59 |
| NA                          |                                 NA |                                   0.04 |                           0.05 |               0.03 |

| Age Group   | Online/mobile banked survey sample | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
|:------------|-----------------------------------:|---------------------------------------:|-------------------------------:|-------------------:|
| 18-25       |                               0.08 |                                   0.11 |                           0.11 |               0.10 |
| 26-35       |                               0.21 |                                   0.23 |                           0.25 |               0.26 |
| 36-49       |                               0.34 |                                   0.33 |                           0.31 |               0.36 |
| 50-64       |                               0.23 |                                   0.18 |                           0.19 |               0.16 |
| 65 and over |                               0.14 |                                   0.11 |                           0.09 |               0.09 |
| NA          |                                 NA |                                   0.04 |                           0.05 |               0.03 |

| Currently Working | Online/mobile banked survey sample | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
|:------------------|-----------------------------------:|---------------------------------------:|-------------------------------:|-------------------:|
| No                |                               0.32 |                                   0.27 |                           0.29 |               0.16 |
| Yes               |                               0.68 |                                   0.69 |                           0.66 |               0.81 |
| NA                |                                 NA |                                   0.04 |                           0.05 |               0.03 |

| Financial Health Tier | Online/mobile banked survey sample | Liquid Account Inflows/Outflows Sample | Liquid Account Balances Sample | Credit Card Sample |
|:----------------------|-----------------------------------:|---------------------------------------:|-------------------------------:|-------------------:|
| Healthy               |                               0.33 |                                   0.27 |                           0.31 |               0.39 |
| Coping                |                               0.56 |                                   0.54 |                           0.50 |               0.53 |
| Vulnerable            |                               0.11 |                                   0.14 |                           0.13 |               0.04 |
| NA                    |                                 NA |                                   0.05 |                           0.06 |               0.04 |

**Table Notes:** The filtered liquid account sample only includes
checking and credit card accounts.This aligns with the filtered liquid
account sample used in our Fall 2021 Pulse Points.

## V. Analytical Decisions

We typically apply several conventions in our analysis of Pulse
transactional data.

**Look-Back Period**

Given the day-to-day noisiness of transactional data and the relative
infrequency of key financial events (e.g., the monthly cadence of many
bills and the relative uncommonness of late fees), we generally
calculate a rolling look-back period over the past 30 days because it
strikes the right balance between temporal accuracy and reduction of
noise.

**Median Values**

When looking at dollar values in the transactional data set, we
typically report the median value to avoid outliers affecting the
trends. For example, when considering trends over a past quarter, we
calculate the median value for each day over the sample. The table below
summarizes the different account groupings we use for analysis, sample
sizes, and metric definitions.

**Activity Thresholds**

We apply basic transaction activity requirements for liquid account
inflows and outflows to ensure we are able to actually observe some
day-to-day transaction activity. We do not apply activity requirements
to other metrics, because transaction activity is less necessary in
those instances to calculate the metric (e.g., an individual can hold a
liquid account balance without having any transactions in the past 6
months).

**Transfers**

Transactions categorized as “transfers” are very common in the
transactional data; they constitute 19% of all outflow transactions and
30% of total transactions. Including transfers in the analysis of
inflows and outflows runs the risk of misidentifying transfers for the
purpose of moving funds between personal financial accounts as income or
expenditures. We generally include transfers in our analysis because we
do not need to directly identify income and expenditures for our metrics
and because any potential double counting may be accounted for in our
analysis. Furthermore, excluding transfers could run the risk of biasing
subsequent analysis against individuals who own investment accounts,
brokerage accounts, or any other type of account where transfers are
common.

## VI. Transactional Metric Definitions

We typically use specific transactional “metrics” to analyze trends in
the Pulse transactional dataset. These metrics align with the
transactional subsamples described in section IV. We describe the
definitions of the most commonly used metrics in Table 3.

*Table 3. Definitions of Metrics*

<img src="https://github.com/financialhealthnetwork/pulse-transactional-methodology-public-/blob/main/pic4.png" width="1000" />

## VII. Study Limitations

**Sample Size** The total sample size of 979 participants in the Pulse
transactional data set limits our ability to examine smaller demographic
subsamples, particularly after we apply inclusion criteria. We are
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
26% of transactions by volume. Given our focus on transaction values and
not transaction volume, this point of comparison suggests that we are
missing a relatively small amount of cash activity in the Pulse
transactional data set.

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
For example, as of October 12, 2021, 51 % of all linked accounts had
become inactive. This attrition generally occurs when user credentials
expire or change, or users voluntarily delink their financial
institutions, resulting in inactive account links. Checking accounts,
savings accounts, and credit card accounts are most likely to attrite.
We hypothesize that this is because frequent use of these accounts
prompts financial institutions to force users to reset their password
more frequently than for other account types. When the user resets their
password with their financial institution, they likely do not also
update it in the UAS Plaid interface.

Our partners at USC send regular reminders to users whose accounts
become inactive to encourage them to relink their accounts. We also
offer participants a $5 incentive to relink accounts that have gone
inactive. However, in practice, very few participants have actively
relinked accounts. We continue to actively examine how to combat
attrition.

**Missing Data**

We are not able to access all transactional data from a given financial
account after a participant initially links or relinks that account.
Although the Plaid API allows us to see past transactions that go back a
limited time period after an account is linked, accounts are deemed
“inactive” in those past dates and balances cannot be observed. We use
[Plaid’s “Assets” product](https://plaid.com/docs/#assets) to capture
historical account balances at the time an individual linked an account,
but attrition and the limits of historical data collection mean we still
face challenges in working with missing data

**Seasonality**

The amount of historical data we are able to gather when an individual
links an account via Plaid limits our current ability to understand the
impact of seasonality on the trends we observe in the Pulse
transactional data set. The amount of time that we are able to look back
into someone’s transactions prior to their linking of an account varies
by account type and institution, though the modal length of time is
about 6 months. Given the majority of our participants first linked
their account(s) in June 2020, we can only retrieve complete data going
back to January 2020 for the majority of the sample. As a result, we
cannot currently compare trends to previous years of data, and thus may
lack some context into which trends are driven by seasonal factors that
might be driving these trends. Furthermore, the unique economic context
in which we have started our data collection may make this period
difficult to use as a baseline for comparison for future data. Over
time, we will gather sufficient data to allow us to compare to previous
years.

## VIII. Looking Ahead

We will continue to analyze trends from the Pulse transactional data set
through the ongoing Pulse Points series and in other analyses. We aim to
improve the data quality and size of the sample over time, making the
transactional data and merged survey and transactional data set even
more valuable. We also intend to make the transactional data set
available for use by other researchers, in addition to the already
[publicly available survey
data](https://finhealthnetwork.org/programs/financial-health-pulse/data/).

Please direct any questions about the transactional data research to
<pulse@finhealthnetwork.org>.
