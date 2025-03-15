# UX_-EXPERIENCE_ANALYSIS
I developed a comprehensive project in Excel using pivot tables and charts, by analyzing user experience to uncover trends and optimize business decisions.

---

## PROJECT OVERVIEW:
Flextrade is a well-known company in the online shopping world, they have been making shopping easier and better for a long time. They sell all kinds of things, from electronics to clothes. Their app is designed to be easy to use, hoping to make shopping fun and simple for everyone. Flextrade wants to keep improving its app to make sure they stay ahead of the competitive online shopping market. This project will look into how they can enhance their app for users. 

---

## PROBLEM STATEMENT:
Even though lots of people download and use the Flextrade app, not everyone ends up buying something. These are the few problems 
1. **High Bounce Rate** - Many users leave the app without buying anything
2. **Cart Abandonment Rate**- Users put items in the cart without completing purchase
3. **Low Average Order Value** - the amount of money users spend is lower than what Flextrade would like
4. **Lots Of Competition** - there are many other shopping apps out there , so Flextrade needs to standout.

---

## DATA SET:
**Data source** - <a href="https://github.com/TawakalituOdebode/UX_-EXPERIENCE_ANALYSIS/blob/main/FlexTrade%20(1).xlsx">Dataset</a> 

**Data Description**
This case study contains 3 datasets;

#### **1. App Analytics Data**
| Column Name         | Description                                            |
|---------------------|--------------------------------------------------------|
| `User_ID`           | A unique identifier for each app user.                |
| `Session_ID`        | A unique identifier for each user's session.           |
| `Timestamp`         | Date and time of the user's activity.                 |
| `Page_Views`        | Number of pages viewed during the session.            |
| `Bounce_Rate`       | Percentage of sessions resulting in immediate exits.  |
| `Add_to_Cart_Rate`  | Percentage of sessions where items were added to the cart. |
| `Conversion_Rate`   | Percentage of sessions that resulted in conversions.  |

#### **2. User Behavior Data**
| Column Name         | Description                                            |
|---------------------|--------------------------------------------------------|
| `User_ID`           | A unique identifier for each app user.                |
| `Session_ID`        | A unique identifier for each user's session.           |
| `Timestamp`         | Date and time of the user's activity.                 |
| `Session_Duration`  | Duration of the user's session.                       |
| `Product_Views`     | Number of products viewed during the session.         |
| `Cart_Additions`    | Number of items added to the cart.                    |
| `Checkout_Progress` | Progress indicator for the checkout process.          |

#### **3. User Feedback Data**
| Column Name         | Description                                            |
|---------------------|--------------------------------------------------------|
| `User_ID`           | A unique identifier for each app user.                |
| `Session_ID`        | A unique identifier for each user's session.           |
| `Timestamp`         | Date and time of the feedback submission.             |
| `Feedback_Type`     | Type of feedback provided.                            |
| `Feedback_Content`  | Textual content of the user feedback.                 |

---

## TOOL USED:
**Data Cleaning and Visualization** - Excel

---

## Key Questions
1. Identify Duplicate Entries: Are there any duplicate user sessions or feedback entries? How can we clean these up?
2. Analyze Session Duration: How long do users typically spend on the app? Are shorter sessions associated with higher bounce rates?
3. Investigate Bounce and Conversion Rates: Is there any significant relationship between both metrics?
4. Understand Cart Behavior: For sessions with cart additions, how often do users proceed to checkout?
5. Feedback Analysis: What common themes can you find in the feedback content?

---

## METHODOLOGY:
1. Convert each dataset sheet into a table using `CTRL + T`.
2. Check for duplicate entries (none found).
3. Consolidate datasets by combining all sheets using the **VLOOKUP** function:
   - Identify common columns (`User_ID`, `Feedback_ID`, and `Timestamp`).
   - Import remaining columns into the `User_Feedback_Data` sheet.
     =VLOOKUP([@[User_ID]], App_Data, 4, FALSE) 
4. Extract year, month, and hour from the `Timestamp` column using the `TEXT` function:
   - Year: `=TEXT([@Timestamp], "YYYY")`
   - Month: `=TEXT([@Timestamp], "MMM")`
5. Create a `Time of Day` column using the `IFS` function:
   =IFS([@[Hour of Day]] >= 21, "Night", [@[Hour of Day]] >= 17, "Evening", [@[Hour of Day]] >= 12, "Afternoon", [@[Hour of Day]] < 12, "Morning")
6. KPI’s  and key questions were calculated using the pivot table.
   
---

## KEY INSIGHTS AND RECOMMENDATIONS:
- With an Industry average bounce rate of 38.70%, the high bounce rate of 49% exhibited by flextrade App indicates that many users leave the site without taking further actions. This suggests a possible UX issue in the early stages of user browsing.
- Cart abandonment – with only 51% of users adding items to their cart, issues during the checkout process are likely to contribute to cart abandonment.
- While the conversion rate varies slightly based on the time of the day, afternoon and night shows high conversion rate (52%). Indicating  preferred time users are likely to complete their purchases.
- The feedback section has highlighted specific UX points such as issues with checkout, search functionalities and occasional app crashes.
  
### RECOMMENDATIONS
- Cart abandonement can be addressed by simplifying checkout process by reducing numbers of steps, displaying clear product and shipping prices. Also sending cart abandonment reminders to prompt users to finish their purchases.
- Flextrade can increase conversion rate during the evening and morning period by offering time-sensitive deals. They can further boost sales in the high performing time by offering sales and discounts.  
- High bounce rate can be drastically reduced by improving page layout and navigation, optimizing load time, improve payment experience and visual appeal, as well as provide excellent customer service by adding live chat support.
- To buffer the effects of high competition Flextrade is experiencing, they can implement upselling and cross-selling strategies like displaying “frequently brought together” or “you might also like”. They can also introduce loyalty and referral programs as well as offer competitive discounts for large purchases.

---

  **In conclusion, These recommendations are aligned with the business goals of improving user experience, reducing cart abandonment, and increasing average order value, all while addressing competition by enhancing customer satisfaction and engagement.**



