# Title: Analyzing Donation Patterns to Enhance Fundraising Strategies

Non-profit organizations (NPOs) play a vital role in addressing societal challenges, providing essential services, and promoting community development. Their ability to create meaningful impact relies heavily on donations from individuals, corporations, and foundations.
DonationHub, a comprehensive database system, aims to streamline and optimize donation processes for NPOs. By providing a centralized platform for storing and analyzing donation data

# Problem Statement
Non-profit organizations struggle to identify effective fundraising strategies due to limited understanding of donor behavior and demographics. This project aims to design and implement a database to store and analyze donation data, providing insights to optimize fundraising efforts and increase donations.

# Tools
SSMS for database management

# Analytical Questions:

``` -- 1. What is the total amount donated?

SELECT SUM(donation) AS TotalDonations
FROM Donation_Data;

-- 2. Which state has the highest total donation amount?

SELECT state, SUM(donation) AS TotalDonations
FROM Donation_Data
GROUP BY state
ORDER BY TotalDonations DESC
LIMIT 1;

-- 3. What is the average donation amount by job field?

SELECT job_field, AVG(donation) AS AverageDonation
FROM Donation_Data
GROUP BY job_field
ORDER BY AverageDonation DESC;

-- 4. Which gender donates more?

SELECT gender, SUM(donation) AS TotalDonations
FROM Donation_Data
GROUP BY gender
ORDER BY TotalDonations DESC;

-- 5. What is the distribution of donation amounts?

SELECT 
  SUM(CASE WHEN donation < 100 THEN 1 ELSE 0 END) AS "< $100",
  SUM(CASE WHEN donation >= 100 AND donation < 500 THEN 1 ELSE 0 END) AS "$100-$499",
  SUM(CASE WHEN donation >= 500 THEN 1 ELSE 0 END) AS ">= $500"
FROM Donation_Data;

-- 6. Which job fields have the most donors?

SELECT TOP 2 job_field, COUNT(*) AS NumDonors 
FROM Donation_Data 
GROUP BY job_field 
ORDER BY NumDonors DESC;

-- 7. What is the correlation between donation amount and shirt size?

SELECT shirt_size, AVG(donation) AS AverageDonation
FROM Donation_Data
GROUP BY shirt_size
ORDER HHBY AverageDonation DESC;

```

# Image
![image](https://github.com/user-attachments/assets/ccfb1c47-1cd7-44f3-8117-47f229f6cdc7)

# Findings:
1. Total donations: $498,170
2. Top donating state: California
3. Highest average donation by job field: Research and Development ($272)
4. Gender donation comparison: Male donors outnumber and outdonate female donors
5. Donation distribution:
    -15.88%  of donations are less than $100
    - 40.8%  of donations are between $100-$499
    - 4% of donations are $500 or more
6. Job fields with most donors:
    - Business Development (188 donors)
    - Engineering (186 donors)
7. Correlation between donation amount and shirt size:
    - Extra Large shirt sizes associated with higher average donations
      
# Recommendations:
Short-Term Strategies:
1. Target California: Focus fundraising efforts in California, leveraging local networks and events.
2. Engage Male Donors: Develop targeted campaigns to encourage male donors to continue supporting the cause.
3. Business Development and Engineering Outreach: Build relationships with professionals in these fields to increase donations.
4. Small Donation Incentives: Offer rewards for donations under $100 to encourage frequent giving.
Long-Term Strategies:
1. Diversify Donor Base: Implement strategies to attract female donors and increase diversity in the donor pool.
2. Research and Development Partnerships: Collaborate with R&D companies to secure larger donations.
3. Extra Large Shirt Size Campaign: Use this correlation to inform merchandise and event strategies.
4. Donation Tiers: Establish clear donation tiers with corresponding benefits to encourage larger donations.
   
# Conclusion:
This analysis provides valuable insights into donation trends and patterns. By implementing these recommendations, the organization can optimize fundraising strategies, increase donations, and build a stronger donor community.


