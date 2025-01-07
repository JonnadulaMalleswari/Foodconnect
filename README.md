# Foodconnect

## Overview
Foodconnect is a Salesforce project aimed at addressing both food waste and food insecurity by creating a solution that connects surplus food suppliers (such as restaurants, grocery stores, and food producers) with individuals and families in need. The goal is to collect food that would otherwise be discarded and redistribute it to those lacking access to nutritious meals.

## Features
- **Surplus Food Connection**: Links food suppliers with individuals in need.
- **User Management**: Allows NGOs to manage their users and volunteers.
- **Custom Reports and Dashboards**: Provides insights into food donations and distributions.
- **Efficient Workflow**: Streamlined process for managing food donations.

## Technology Stack
- **Salesforce**: For customer relationship management and application development.
- **Apex**: Salesforce's programming language for backend logic.
- **Visualforce**: For creating user interfaces in Salesforce.

## Installation
To install and set up the project, follow these steps:
1. **Create a Salesforce Developer Account**:
   - Visit the [Salesforce Developer Signup Page](https://developer.salesforce.com/signup).
   - Fill out the required details and submit the form.
   - Check your email for a verification link, set up a password, and complete the account setup process.

2. **Object Creation**:
   - Navigate to Setup > Object Manager > Create > Custom Object and create the following objects:
     - Venue
     - Drop-Off Point
     - Task
     - Volunteer
     - Execution Detail

3. **Tabs Creation**:
   - Create custom tabs for each object by navigating to Setup > Quick Find > Tabs > Custom Object Tabs > New.

4. **Create a Lightning App**:
   - Navigate to Setup > Quick Find > App Manager > New Lightning App.
   - Add Home, Venue, Drop-Off Point, Task, Volunteer, Execution Details, and Reports.

5. **Field and Relationship Creation**:
   - Create Lookup and Master-Detail relationships between various objects.
   - Create fields such as Email, Phone, Geolocation, Text Area, Picklist, Auto Number, and Formula.

6. **Flow Creation**:
   - Navigate to Setup and create a Screen Flow for the Venue object.

7. **Trigger Creation**:
   - Create a trigger on the Drop-Off Point object to calculate the Distance field.

   ```apex
   trigger DropOffTrigger on Drop_Off_point__c (before insert) {
       for(Drop_Off_point__c Drop : Trigger.new) {
           Drop.Distance__c = Drop.distance_calculation__c;
       }
   }
8.Profiles and User Creation:

Clone the Standard Platform User profile to create a new profile called NGOs Profile.
Create users for different NGOs.

9.Public Groups Creation:

Create public groups such as Iksha, NSS, and Street Cause.


10.Report Types and Reports Creation:
Create custom report types and corresponding reports for analysis.


11.Dashboard Creation:

Create custom dashboards and add relevant reports.


12.Sharing Rules Creation:

Create sharing rules for the Drop-Off Point object based on Distance field values.


13.Home Page Creation:

Create a custom home page for the app using the Lightning App Builder.


14.Conclusion
By leveraging Salesforce for this project, we created an efficient system for managing food donations. It connects surplus food suppliers with individuals in need, maximizing resource utilization and effectively addressing food insecurity.
