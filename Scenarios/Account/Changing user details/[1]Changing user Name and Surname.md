**Title:** [1]Changing user Name and Surname

**Preconditions:** User is logged in

**Test steps:**
1. click "Edytuj dane osobowe"
	1. you should be at /dashboard/account/profile url
2. change values at "Imię" and "Nazwisko" field
	1. red button "Zapisz" should be visible
3. click button "Zapisz" at the bottom of the screen
	1. button should be inactive, and popup with "Zmiany Zostały zapisane" should appear at the top right corner
	2. Name and Surname at /dashboard/account should be changed

**Expected result:** User is able to change his name and surname without any errors via "Edytuj dane osobowe" flow and his new Name and Surname should be visible at /account url