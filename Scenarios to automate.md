### Below I will list test cases which in my opinion should and can be automated :)

- **[1]Changing user Name and Surname** - pretty basic feature, used not so often, but easy to automate and assert
- **[2]Changing user Email** - in my opinion actually important feature, in the interviewme app easy to automate because lack of the email confirmation, as well as easy to assert just for string change.
- **[3]Changing user Password** - major case to automate, just like email, it's a pleasure without any emails, codes etc to confirm changes. Assert may be done by executing login script, or by api.
- **[4]Changing Privacy Policy and Regulations** - or maybe deleting account should be its name? I think it's pretty obvious to have an automated test for deleting an account. Should be easy to automate

- cases [4],[5],[6],[7] and [8] may be also automated, but one day someone told me that automating something that changes really often isn't the greatest idea. If we would have some mocked offers it will be ok, but it can't be forever the same of course.

**In addition to above**, I think it's always a good thing to automate cases which aren't hard to automate, won't change in days, are pain in the neck to test because of its repeatability, and are just cases to mark as done.