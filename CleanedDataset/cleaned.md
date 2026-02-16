**Data** **Cleaning** **Documentation**

**Capstone** **G17** **Transaction** **Dataset** **Dataset**

**1.** **Objective**

The primary objective of this data cleaning process was to transform the
raw transactional dataset into a reliable, consistent, and
analysis-ready format suitable for business intelligence and dashboard
development.

The original dataset contained approximately 10,000 transaction records.
However, it included multiple data quality issues such as missing
values, inconsistent formatting, invalid numeric entries, placeholder
values, and duplicate records. These issues could negatively impact
analytical accuracy, distort key performance indicators (KPIs), and lead
to incorrect business insights.

The cleaning process focused on improving data integrity, ensuring
logical consistency, and preserving maximum valid data while removing or
correcting corrupted records.

**2.** **Column** **Name** **Standardization**

Column names were standardized to ensure structural consistency and
compatibility with analytical workflows.

Issues observed included inconsistent naming formats, mixed
capitalization, and spaces in column names. These inconsistencies can
cause errors during data processing and make data handling inefficient.

Column names were standardized using the following principles:

> ● Converted all names to lowercase
>
> ● Removed unnecessary spaces
>
> ● Used underscores for separation

This ensured uniform naming conventions and improved usability for
analysis and visualization.

**3.** **Removal** **of** **Whitespace** **and** **Text**
**Normalization**

Several categorical fields, including item, payment_method, and
location, contained leading and trailing whitespace.

Whitespace inconsistencies can result in the same category being
interpreted as multiple distinct values, leading to incorrect
aggregation and misleading analytical results.

For example:

> ● "Cash" and " Cash " would be treated as different categories

Whitespace normalization ensured that categorical values were consistent
and properly grouped during analysis.

**4.** **Handling** **of** **Invalid** **Placeholder** **and**
**Corrupted** **Values**

The dataset contained non-informative placeholder values such as:

> ● ERROR
>
> ● Unknown
>
> ● nan
>
> ● null

These values do not represent valid business transactions and can
disrupt categorical analysis and reporting.

These placeholders were systematically identified and replaced with
valid

business-appropriate categories or removed where necessary. This ensured
that all categorical fields represented meaningful and analyzable
information.

This step improved categorical data integrity and ensured accurate
grouping and filtering.

**5.** **Numeric** **Data** **Validation** **and** **Correction**

The quantity and price_per_unit fields are critical financial variables
that directly influence revenue calculations.

Issues identified included:

> ● Missing numeric values
>
> ● Improperly formatted numeric entries
>
> ● Zero or invalid values

To preserve valid records and maintain statistical consistency, missing
numeric values were handled using appropriate imputation techniques
rather than deleting entire records.

This ensured:

> ● Logical completeness of financial data
>
> ● Prevention of calculation errors
>
> ● Preservation of dataset size and analytical coverage

Ensuring numeric integrity is essential for accurate revenue analysis
and KPI computation.

**6.** **Revenue** **Consistency** **and** **Recalculation**

The total_spent field represents transaction revenue and must logically
align with quantity and price_per_unit.

Data inconsistencies were identified where revenue values did not
correctly correspond with the associated quantity and unit price.

To ensure financial accuracy, revenue values were recalculated based on
validated quantity and price values.

This ensured:

> ● Financial consistency across all transactions
>
> ● Accurate total revenue calculation
>
> ● Reliable KPI and performance metrics

This step was critical to maintaining financial data integrity.

**7.** **Handling** **Missing** **Categorical** **Values**

Categorical fields such as location and payment_method contained missing
entries.

Instead of removing these records entirely, missing categorical values
were replaced with valid existing categories based on realistic business
distribution.

This approach was selected because:

> ● The transaction itself remained valid
>
> ● Only categorical classification was missing
>
> ● Removing such records would unnecessarily reduce dataset size

This method preserved valuable transactional data while maintaining
categorical consistency.

**8.** **Removal** **of** **Logically** **Invalid** **Records**

Certain records contained logically impossible values, such as:

> ● Quantity equal to zero
>
> ● Price per unit equal to zero or negative

These values do not represent valid business transactions and could
distort revenue calculations and analytical outcomes.

Such records were removed to ensure that the dataset reflected only
legitimate and meaningful transactions.

This step ensured logical validity and analytical accuracy.

**9.** **Standardization** **of** **Date** **Format**

The transaction_date field contained inconsistent and improperly
formatted date values.

Date standardization ensured that all transaction dates were recognized
as valid date-time values, enabling accurate time-based analysis such
as:

> ● Monthly sales trends
>
> ● Year-wise performance analysis
>
> ● Seasonal and temporal insights

Proper date formatting is essential for time-series analysis and
business reporting.

**10.** **Duplicate** **Record** **Identification** **and** **Removal**

Duplicate transaction records were identified within the dataset.

Duplicate records can significantly distort analysis by:

> ● Inflating revenue calculations
>
> ● Increasing transaction counts artificially
>
> ● Creating inaccurate business metrics

Duplicate entries were removed to ensure that each transaction was
uniquely represented.

This ensured transactional integrity and analytical reliability.

**11.** **Final** **Data** **Validation** **and** **Quality**
**Assurance**

Following the cleaning process, the dataset underwent comprehensive
validation to ensure:

> ● No invalid placeholder values remained
>
> ● No missing or blank critical fields existed
>
> ● All numeric values were logically valid
>
> ● Categorical values were consistent
>
> ● No duplicate records remained
>
> ● Revenue values were accurate and consistent

This validation ensured high data quality and analytical readiness.

**12.** **Final** **Outcome**

The data cleaning process significantly improved the overall quality,
consistency, and reliability of the dataset.

Key improvements achieved:

> ● Removal of invalid and corrupted records
>
> ● Correction of numeric and financial inconsistencies
>
> ● Standardization of categorical and date values
>
> ● Elimination of duplicate transactions
>
> ● Preservation of valid transactional data

The final cleaned dataset contains 6,658 valid transaction records and
is fully prepared for business analysis, dashboard creation, and KPI
reporting.

**13.** **Conclusion**

Through systematic data cleaning and validation, the dataset was
transformed from a raw, inconsistent state into a structured and
reliable analytical dataset.

The cleaning process ensured data integrity, financial accuracy, and
analytical consistency, enabling accurate business insights and reliable
decision-making.

The dataset is now fully suitable for advanced analysis, visualization,
and business intelligence applications.
