# LinkedIn Datasets

Field documentation for Kipplo's three LinkedIn datasets: companies, professional profiles and job postings.

**[Explore the full LinkedIn datasets on Kipplo](https://www.kipplo.com/datasets/linkedin-datasets/?utm_source=github&utm_medium=repo&utm_campaign=linkedin-datasets)**

*Note: This repository is maintained independently by Karthik V from Kipplo's marketing team and is not an official Kipplo repository.*

---

## About these datasets

A Kipplo LinkedIn dataset is a ready-built table of company profiles, people profiles or job postings, assembled from public and licensed sources. Instead of looking records up one at a time, you filter the complete dataset down to your segment and export the rows you need in one go.

Kipplo offers three:

- **LinkedIn Company Dataset:** one row per company, with its size, industry, location, technology stack, funding, team composition and open roles
- **LinkedIn Profile Dataset:** one row per person at work, with their job title, seniority, department, employer and location, plus any work email and direct dial Kipplo holds for them
- **LinkedIn Job Posting Dataset:** one row per job posting, active or closed, showing who is hiring, for what role, where, and at what pay

| Detail | Value |
|---|---|
| Datasets | 3, all live |
| Coverage | Global |
| Refresh | Continuous |
| Formats | CSV, XLSX, JSON, XML, SQL |
| Access | Data Explorer, API, cloud delivery on request |

---

## Dataset overview

| Dataset | Records | Fields | One row is | Record key |
|---|---|---|---|---|
| [LinkedIn Company Dataset](https://www.kipplo.com/datasets/linkedin-company-dataset/?utm_source=github&utm_medium=repo&utm_campaign=linkedin-datasets) | 60M+ | 73 | a company | `company_domain` |
| [LinkedIn Profile Dataset](https://www.kipplo.com/datasets/linkedin-profile-dataset/?utm_source=github&utm_medium=repo&utm_campaign=linkedin-datasets) | 250M+ | 73 | a professional | `linkedin_url` |
| [LinkedIn Job Posting Dataset](https://www.kipplo.com/datasets/linkedin-jobs-dataset/?utm_source=github&utm_medium=repo&utm_campaign=linkedin-datasets) | 10M+ | 34 | a job posting | `job_posting_id` |

## How the datasets connect

- **Profile to Company:** every profile row carries the person and their employer together, and the Profile Dataset joins onto the Company Dataset by company domain
- **Job Posting to Company:** `company_linkedin_url` on each posting is the join key to the Company Dataset
- Used together, they support prospecting, account-based marketing, talent and research workflows

---

## LinkedIn Company Dataset

Firmographic data for 60M+ companies worldwide: one row per company domain. Every field describes the organisation, with no personal names, emails or individual profiles.

**73 fields in 8 groups**

| Group | Fields |
|---|---|
| Identity (6) | `company_name`, `company_domain`, `company_linkedin`, `company_description`, `specialities`, `company_name_language` |
| Classification (8) | `industry`, `linkedin_industry`, `naicscodes_v5`, `naics_description`, `siccodes_v5`, `sic_description`, `company_entity_type`, `company_legal_type_text` |
| Size and revenue (9) | `headcount_range`, `headcount_min`, `headcount_max`, `employee_on_linkedin`, `employee_on_linkedin_growth_rate`, `revenue_range`, `revenue_min`, `revenue_max`, `year_founded` |
| Location and contact (11) | `company_hq_country`, `company_hq_state`, `headquarters_city`, `company_country`, `company_state`, `company_city`, `company_address`, `postcode`, `country_region`, `location_count`, `company_phone` |
| Funding (6) | `total_funding_amount`, `last_funding_amount`, `last_funding_date`, `last_funding_type`, `funding_round_num_investors`, `lead_investors` |
| Technology and web (7) | `company_technologies`, `technology_name`, `technology_id`, `monthly_google_adspend`, `total_monthly_traffic`, `monthly_organic_traffic`, `monthly_paid_traffic` |
| Team composition (14) | employees by function: `engineer_role_count`, `devops_role_count`, `it_role_count`, `security_role_count`, `network_infrastructure_role_count`, `qa_role_count`, `mobile_dev_role_count`, `ios_dev_role_count`, `android_dev_role_count`, `sales_role_count`, `business_development_role_count`, `marketing_role_count`, `customer_success_role_count`, `operations_role_count` |
| Hiring signals (12) | open vacancies by function: `account_executive_open_roles_count`, `business_development_open_roles_count`, `customer_success_open_roles_count`, `demand_generation_open_roles_count`, `devops_open_roles_count`, `grc_open_roles_count`, `it_open_roles_count`, `marketing_open_roles_count`, `network_infrastructure_open_roles_count`, `operations_open_roles_count`, `sales_open_roles_count`, `security_open_roles_count` |

**Selected definitions**

| Field | Definition |
|---|---|
| `company_domain` | Primary web domain, and the key for each record |
| `industry` | Normalised industry label |
| `linkedin_industry` | Industry label as LinkedIn reports it, before normalisation |
| `employee_on_linkedin` | Employees with a profile listing the company |
| `employee_on_linkedin_growth_rate` | Change in that employee count over the trailing period |
| `revenue_range` | Estimated annual revenue band |
| `company_hq_country` | Country of the registered headquarters |
| `company_country` | Country of the primary listed location |
| `monthly_google_adspend` | Estimated monthly Google Ads spend, in USD |
| `*_role_count` | Employees in that function with a profile listing the company |
| `*_open_roles_count` | Open vacancies counted in that function |

**Filters:** 60, including headcount, revenue, industry, NAICS and SIC codes, HQ location, technology, funding, website traffic, open roles and team composition.

**Common uses:** sizing an addressable market from real records, mapping an industry and benchmarking its players, reading hiring and team composition, and building research tools, dashboards and enrichment pipelines on top of the data.

**[See the LinkedIn Company Dataset](https://www.kipplo.com/datasets/linkedin-company-dataset/?utm_source=github&utm_medium=repo&utm_campaign=linkedin-datasets)**

---

## LinkedIn Profile Dataset

250M+ professional profiles. Each row holds the person and their employer together, so company name, domain, industry, headcount, revenue, technologies, open roles and funding all sit on the same row.

**73 fields in 10 groups**

| Group | Fields |
|---|---|
| Person (13) | `full_name`, `firstname`, `middlename`, `lastname`, `linkedin_url`, `linkedin_headline`, `job_title`, `job_description`, `seniority`, `department`, `about`, `Skills`, `Specialities` |
| Contact (4) | `business_email`, `email_status`, `secondary_email`, `cell_phone` |
| Person location (5) | `country`, `state`, `city`, `country_region`, `continent` |
| Company (7) | `company_name`, `company_domain`, `company_linkedin`, `company_description`, `company_legal_type`, `company_entity_type`, `company_name_language` |
| Company location (10) | `company_country`, `company_state`, `company_city`, `company_address`, `postcode`, `company_phone`, `company_hq_country`, `company_hq_state`, `company_hq_city`, `location_count` |
| Industry classification (5) | `linkedin_industry`, `sic_codes`, `sic_description`, `naics_codes`, `naics_description` |
| Size and scale (5) | `headcount_range`, `revenue_range`, `year_founded`, `employee_on_linkedin`, `employee_on_linkedin_growth_rate` |
| Technology and web (6) | `technologies`, `Company Technologies`, `monthly_google_adspend`, `total_monthly_traffic`, `monthly_organic_traffic`, `monthly_paid_traffic` |
| Open roles (12) | open roles by function, from `it_open_roles_count` to `security_open_roles_count` |
| Funding (6) | `lead_investors`, `total_funding_amount`, `last_funding_amount`, `last_funding_date`, `funding_round_num_investors`, `last_funding_type` |

**Selected definitions**

| Field | Definition |
|---|---|
| `linkedin_url` | Canonical profile URL, and the stable key for matching |
| `seniority` | Normalised seniority tier |
| `department` | Normalised function |
| `email_status` | Deliverability status of the business email |
| `cell_phone` | Direct dial, where a validated number exists |

**Filters:** 64, across person, contact, location, company, classification, technology, open roles, funding and traffic.

**Common uses:** building outbound lists by seniority, function and country; finding candidates by title, seniority and department; and sizing a market by counting the real number of people in a role and region.

**[See the LinkedIn Profile Dataset](https://www.kipplo.com/datasets/linkedin-profile-dataset/?utm_source=github&utm_medium=repo&utm_campaign=linkedin-datasets)**

---

## LinkedIn Job Posting Dataset

A bulk dataset of 10M+ job listings published on LinkedIn, active and closed, from employers worldwide. Titles, full descriptions, locations and listing dates sit alongside the employer's industry, size and head office.

**34 fields in 7 groups**

| Group | Fields |
|---|---|
| The role (4) | `job_title`, `job_description`, `job_location`, `source_domain` |
| Dates (2) | `listed_at`, `expire_at` |
| Hiring company (6) | `company_name`, `company_linkedin_url`, `company_description`, `company_specialities`, `company_industries`, `company_head_count` |
| Company location (6) | `company_location`, `company_hq_country`, `company_hq_state`, `company_hq_city`, `company_hq_street`, `postal_code` |
| Compensation (4) | `min_salary`, `max_salary`, `pay_period`, `compensation_type` |
| Role attributes (7) | `formatted_employment_status`, `formatted_experience_level`, `work_remote_allowed`, `job_functions`, `formatted_job_functions`, `industries`, `formatted_industries` |
| Posting identifiers (5) | `job_posting_id`, `job_posting_url`, `company_apply_url`, `original_posted_time`, `job_state` |

**Selected definitions**

| Field | Definition |
|---|---|
| `job_posting_id` | Identifier for the posting, and the stable key for the table |
| `company_linkedin_url` | Company LinkedIn profile URL, and the join key to the Company Dataset |
| `listed_at` | When the listing was most recently seen live |
| `original_posted_time` | When the posting first went live |
| `job_state` | Current state of the listing, such as active or closed |
| `formatted_experience_level` | Seniority the employer asked for, such as mid-senior level |

**Filters:** 10, across the role, the hiring company and its headquarters.

**Common uses:** spotting companies that are expanding their teams, tracking demand by role and market over time, mapping which employers compete for the same talent, building recruiting and market-intelligence products, and extracting the tools and platforms named in job descriptions as adoption signals.

**[See the LinkedIn Job Posting Dataset](https://www.kipplo.com/datasets/linkedin-jobs-dataset/?utm_source=github&utm_medium=repo&utm_campaign=linkedin-datasets)**

---

## Full datasets

**[Explore the full LinkedIn datasets on Kipplo](https://www.kipplo.com/datasets/linkedin-datasets/?utm_source=github&utm_medium=repo&utm_campaign=linkedin-datasets)**

Data from [Kipplo](https://www.kipplo.com/?utm_source=github&utm_medium=repo&utm_campaign=linkedin-datasets), a B2B data platform for growth teams.
