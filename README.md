# Rivalry-Beyond-Campus:Identifying-Real-Estate-Opportunities-for-School-Districts-using-Machine-Learning

## Table of Content
- [ABSTRACT](#abstract)
- [TASK DESCRIPTION](#task-description)
- [MAJOR CHALLENGES AND SOLUTIONS](#major-challenges-and-solutions)
- [DATA DESCRIPTION](#data-description)
- [WORKFLOW AND ANALYTIC TECHNIQUES](#workflow-and-analytic-techniques)
- [SUMMARY](#summary)

## ABSTRACT
In view of the increased uncertainty in the real estate market over the pandemic of COVID-19, it is more important for investors and customers to avoid uninformed decisions. In this project, we built a machine learning framework to estimate expected value of residential properties in the university district of both UCLA and USC. We developed a set of regressors over tax assessment data and Zillow housing data and identified 5 investment opportunities for each school district. We also explained such results based on a naïve value discovery mechanism. The Stacked Ensemble model and SVR model in our system showed best out-of-sample performance in terms of MAE and MSE respectively. The district of UCLA is a better submarket in term of its higher opportunity density.

## TASK DESCRIPTION
1. Explore the major drivers for the value of properties.
2. Identify at least 5 investment opportunities of residential properties for both UCLA district and USC district, and answer which school district is the winner overall.

## MAJOR CHALLENGES AND SOLUTIONS
Based on the structural nature and expected functions of our predictive framework, there are at least two major challenges that should be understood properly: the determination of opportunity discovery mechanism and the data proxy issue.

### A. Opportunity Discovery Mechanism
We believe that the price of a property would deviate from its expected value due to some uncaptured information and unpredictable factors. We use 𝑝𝑖 and 𝑝̅𝑖 to denote the market price and expected value of property 𝑖. The property would be identified as an investment opportunity when 𝑝𝑖<𝑝̅𝑖, because it could generate immediate profit if sold right after its purchase, assuming no significant transaction costs. Then, we would be able to train a machine learning model 𝑓: ℝ𝑑→𝑝̂𝑖 over 𝑑 dimensional data to estimate 𝑝̅𝑖 for each in-sample property. And if 𝑝𝑖<𝑝̂𝑖 , the model predicts property 𝑖 is an opportunity.

### B. Proxy Selection
Based on the opportunity discovery model proposed above, the next challenge is collecting relevant data to make model estimations reasonable. As we know, for property 𝑖, its expected value 𝑝̅𝑖 is always unrevealed. Feeding the model with proper proxies is important to the model success. Also, although market price 𝑝𝑖 is always available on paper, the majority of records are associated with closed deals. So, these backward-looking signals would introduce the risk of bad generalization, thus making our application unpractical.

To address these problems, we choose the tax-based assessor parcels data as our major dataset to estimate the expected value of properties. We believe it would contribute as a good proxy because unreasonable evaluations directly lead to tax loss or crisis of social justice. Besides, we turn to Zillow data to make sense of the market as well. To be specific, we use prices of historical deals to adjust the estimation of 𝑝̅𝑖, and choose real-time listing prices of properties for sale as the proxy of 𝑝𝑖 to make our predictions forward-looking.

## DATA DESCRIPTION
The datasets used in this project can be roughly divided into three categories: location data, property characteristics data, and price data. The location data and property characteristics data are obtained from Assessor Parcels Data as part of County of Los Angeles open data, the price data is collected from the same dataset and extra Zillow housing data.

The raw datasets include 38 million properties with descriptions for parcels on the assessor's annual secured assessment rolls from 2006 to 2021. In order to have a good consistency between datasets, we filtered properties by restricting their assessment roll year between 2013 and 2021. Selected features are summarized as Table I.

| Name | Description  |
| :--: |    :-:   |
| Location Features |
| zip2 | The 5-digit zip code that matches property’s actual street address |

<table>
    <caption>TABLE I. SELECTED FEATURES AND TARGET</caption>
    <tr>
        <td align="center">Name</td>
        <td align="center">Description</td>
    <tr>
    <tr>
        <td colspan="2" align="center">Location Features</td>
    <tr>
    <tr>
        <td>zip2</td>
        <td>The miles distance away from UCLA</td>
    <tr>  
    <tr>
        <td>distance_to_usc</td>
        <td>The miles distance away from USC</td>
    <tr>  
    <tr>
        <td>PropertyLocation</td>
        <td>The actual address of the property (used to match real-time listing price)</td>
    <tr> 
    <tr>
        <td colspan="2" align="center">Property Characteristics Features</td>
    <tr>
    <tr>
        <td>Bedrooms</td>
        <td>The total number of bedrooms</td>
    <tr>
    <tr>
        <td>Bathroom_per_bedroom</td>
        <td>The total number of bathrooms/ total number of bedrooms</td>
    <tr>
    <tr>
        <td>Units</td>
        <td>The total number of living units</td>
    <tr>
    <tr>
        <td>YearBuilt</td>
        <td>The year property was originally built</td>
    <tr>
    <tr>
        <td>Years_until_effective</td>
        <td>The number of years between build year and effective year</td>
    <tr>
</table>


## WORKFLOW AND ANALYTIC TECHNIQUES
vrvrvrv

## SUMMARY
