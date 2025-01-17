## Installation ##
```pip install -r requirements.txt```<br/>
```python manage.py runserver```


### Go to: ```http://localhost:8000/home/```

## Hospital side login: ##
Uname: rajesh<br/>
Pass: rajesh14

## Donor side login: ##
Uname: hemanth<br/>
Pass: rajesh15

### Please note that if you use existing db, all the forgot password emails will be directed to "rajesh.gupta@dal.ca". Hence, create a new user in the existing DB to test such features. ###

## To create new db and delete existing details: ##
- Delete db.sqlite3 file
- Delete migrations/ folder inside donors/ and hospitals/ folder

## Run these commands: ##
```python manage.py makemigrations hospitals donors```<br/>
```python manage.py migrate```

## Working instructions on hospital side ##
Login: Secure access for authorized hospital staff.
Dashboard: Overview of pending tasks (appointments and donations).
Appointment Approvals: Review and approve/deny donor appointments.
Donation Approvals: After appointment approval, manage donation requests.
Search Donations: Search for specific donations based on medical or donor criteria.
- Open a browser and visit http://localhost:8000/hospitals/login/ to login.
- The home page displays an action items tab which gives the summary of number of pending appointments and pending donations.
- The count displayed is dynamic and gets updated automatically as and when the appointment/donation requests come for approval.
- Switch to 'Pending appointment approvals' tab by either clicking on the action item card or by manually navigating to the tab.
- A list of pending appointments will be displayed.
- Select a record and click on 'Details' button, the details of the appointment will be displayed below the table.
- Select a record and click on 'Approve' button, the appointment will be approved and the donation will be moved to the 'Pending donation approvals' tab. 
- If an appointment is denied, the donation request will not be eligible for getting approved or denied. That is, the donation request will not be moved to 'Pending donation approvals' tab.
- Click on 'Pending donation approvals' tab to view the pending donations. Alternatively this tab can also be selected by clicking on the corresponding card in the home screen.
- Select a donation record and click on 'Details' button, the details of the donation will be displayed below the table.
- Select a donation record and click on 'Approve' button, the donation will be approved. Likewise, the donations can also be denied.
- Navigate to the 'Search donations' tab. Enter any keyword related to the donation, such as organ/blood group/donor first name/donor last name/donation ID (For eg: Kidney/Hemanth) and click on search button. 
- From the search results displayed, select a record and click on the 'Details' button. The entire details of the donation will be displayed below the table. Note that only the approved donations will be displayed in the search results. 

## Note ## 
For viewing the database records, kindly follow the below steps:
- Stop the server by pressing CTRL + C
- Run python manage.py createsuperuser
- Enter neccessary details such as username, email, and password
- Launch the server again using python manage.py runserver 
- Visit http://127.0.0.1:8000/admin/ and login using the username and password that was created in step 3. 
- The users table consists of user records, the appointments table consist of appointment information, and the donation requests table contains donation related information.
   
## Working instructions on donor side ##
- Open a browser and visit http://localhost:8000/donors/login/ to login.
- Create Donation Request and create a corresponding appointment for that donation request.
- View Donation History on homepage
