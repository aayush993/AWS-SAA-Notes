To make sure least amount of money is spent. That’s why it’s good to setup a budget to get notification when we go over the budget.

<aside>
💡 My Account > My Billing Dashboard

</aside>

We can setup a billing alarm using a root user. But for IAM user we need a separate permission which has to be provided by root user. 

<aside>
💡 My Account > Scroll Down > IAM User and Role access to Billing Information > Check Activate

</aside>

Activating above does not guarantee access to all IAM users. IAM user should have necessary permissions and policies attached to access billing page. 

Once in billing dashboard. We have information regarding our costs. 
Let’s find out how to find out source of this costs. 

Go to bills, check grand total. 
Go to charge by service, and drill down the service which has incurred charges. 

Once the service is identified, go to the region then go to the service and delete the particular resource. 

Go to Free tier, to find out what is the free tier usage and what is your usage. 

To get alerts best thing is to create a budget.

Go to Budgets, Create a Budget. 
In Setup, Use a template > Zero spend budget > add name > email > create 

In Setup, Use a template > Monthly spend budget > amount > add name > email > create