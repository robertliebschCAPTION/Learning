1: ITSD Ticket
	must have Full name, Job Title, Manager, Start Date, Zenefits number, personal email, phone number and address
2: Create Google Account
	navigate to the appropriate OU based on JobTitle
	Click Add new user
		Enter Fill in First, Last, Primary email
		Enter default Password
	Open created User Object: User Information
		Complete Contact Information
			personal email, phone number, address
		Complete Employee Information
			Employee ID (Zenefits number), Job Title, Manager's email, Department
		Single Sign-On
			add TeamViewer Customer Identifier
	Open Groups
		Add Team, Employees, Department. Additionally, Per RBAC Masterlist row 10 add appropriate groups
	Open Shared Drives
		Per RBAC Masterlist row 4, add appropriate Shared Drives
3: Start computer Build (get on wifi, or get on ethernet)
	If DEP enabled
		Continue to Remote Management
		Create a Computer Account in format: firstlast
		create default password
		when Finder is   open Terminal
			tail -f /var/log/jamf.log
		after all policies complete go to 4
	If manually enrolled
		create user account in format: firstlast
		create default password
		open safari to https://captionhealth.jamf.com/enrol
			when prompted install Cert
			when prompted install MDM
		Open Terminal 
			tail -f /var/log/jamf.log
		after all policies complete go to 4
	If user needs Adobe Creative/DC or Microsoft Office add them to appropriate Static Group
		Microsoft Office: https://captionhealth.jamfcloud.com/policies.html?id=19&o=r
		Adobe Suite/DC: https://captionhealth.jamfcloud.com/policies.html?id=25&o=r
4: Preconfigure System
	Open System Preferences: General
		Set Default Web Browser to Google Chrome
	When Code42 prompts
		login with info from 2
		server is clients.us.code42.com
		SSO will manage the rest
	Launch Google Chrome
		Sign in to Browser with information from 2
			NB: Defer 2FA
			Turn on Sync, Link Data, Yes, I'm in
		Approve Browser at https://admin.google.com/ac/devices/list?status=6&category=all&hl=en
		Confirm Caption Health Bookmarks and Extensions load.
		Go to Caption Health: Mail
			Enable notifications, Activate Virtru
		Go to Caption Health: Calendar
			Enable notifications, Add Caption Health calendar
		Log into Zoom Scheduler (SSO)
	Launch Zoom
		Log In with info from 2
		When Chrome tries to launch Zoom.us check the "always allow" when opening the Zoom.us app
		Click New Meeting
			in System Preferences: Security & Privacy: Privacy
				Click the Lock and authenticate
				Scroll to Camera: click box next to zoom.us
				Scroll to Microphone: click box next to zoom.us
				Scroll to Accessibility: + to add zoom.us
				Scroll to Screen Recording: + to add zoom.us
	Launch Slack
		Allow access to files in Downloads (OK)
		
		Log In with info from 2
			detail process needed
			should we enable Slack like Zoom?
			Sign into your workspace caption-health
			This doens't always redirect to Slack.app
				may need to repeat then select Caption Health to launch in Slack.app
	Launch Google Drive
		Log in with info from 2
	In Chrome go to Caption Health: Service Center
		Create account
	Reboot System and enable FileVault (if you don't kicked back to login)
	If Adobe Creative/DC
		Go to https://adminconsole.adobe.com/889568055E56EA120A495FA8@AdobeOrg/products
			Click Assign Users under appropriate product
			enter user email
			select Product Profile
			Click Save
	If Microsoft
		Go to https://admin.microsoft.com/Adminportal/Home?source=applauncher#/users
			Click Add a user
			enter First and Last name
			set username to email created in 2
			change domain to captionhealth.com
			set password to default
			email the new password to enter the email address of the user (add ;your email if you want a copy)
			Add Product Microsoft 365 Apps for business
			Open the accounnt you created
			Click Licenses and apps
			Click the blue down carat near Apps
			Deselect Office for the web
			Deseelect OneDrive for business
			Complete account creation
	If Adobe/Microsoft
		Add users to JAMF Policy "Install CCDA and Acrobat Pro" and/or "Install Office from Web"
			in terminal "sudo jamf policy"
		Launch Creative Cloud and authenticate
			there could be an update to CCDA
		Launch Word and Authenticate
		Check all configs are valid
5: Move user to Limited OU
6: Asset Panda
	Go to https://login.assetpanda.com/employees
	Click Add New
		provide all info, change status to Active
	Go to https://login.assetpanda.com/asset_items
		Search for the Serial number of the computer (about this mac or bottom of laptop)
		set Assigned To to the new user
		set Location to Home Office
		set Status to Assigned to Employee
7: Adobe Sign
	Go to https://adminconsole.adobe.com/889568055E56EA120A495FA8@AdobeOrg/products/25037FE7A5A7EE66BDFA/users
	Click Add User
		Search for User and select
		Click Select Product Profiles and select Default Adobe Sign - Enterprise configuration
		Click Save
	Go to https://caption-health.na2.echosign.com/account/homeJS
		Click Start from Library
		Search for Company Issued Equipment Agreement Form
		Enter your email first
		Enter user from 2
		Click Send
		Enter Users's info from Start Ticket (Name, Position, Employee#, Manager
		Enter Laptop Make and Model (easiest to copy from JAMF)
		Enter Monitor info (if available)
		Enter NA for Mouse/Keyboard and Other
		Enter YOUR Job Title
		Click to Sign
		Click blue button to Sign and Send
8: quit all apps. Shut down. Wipe down, pack it up, ship it out.
9: Move user to Limited OU. This will restrict access to only what is needed pre-HIPAA training
10: Orientation
	Meeting set by Jess.
	Join Zoom.
	Give user default password, have them log in.
	Have user join home Wifi
	System Preferences: Users & Groups: Change Password 9char minimum, upper, lower, numeric, non-numeric
	System Preferences: TouchID
	Launch Chrome go to https://myaccount.google.com
	Authenticate with default password
	Click Security in left Pane
	scroll to Password
		reset password 12char min, upper, lower, numeric, non-numeric
		back arrow
	2-step verification
		get Google app on phone for prompt
		Add Phone 
		back arrow
	Show them Gmail
	Show them Calendar
	Launch Zoom (send invite to their caption address)
	Launch Slack
	Tour Drive
	Send 1Password Invite
		explain password requirement
		Direct user to email
		enter full name, continue
		create master password,
		follow prompts
		mobile phone: enter phone number, verify, continue
		pick your phone
		Automatically Send Push When I log in
		continue to login, Send a push to finalize

	Have user get Duo
	1Password walkthrough
	Link to Duo
11: iPhone
	Find Google Device Policy in App Store
		Download, open, scroll past intro, continue, allow, get started,
	Click continue , continue, sign in captionhealth, password, 2FA, Accept, install profile (blule circle down arrow), Allow, Close
	Settings, Profile Downloaded, Install, Passcode, Install Profile Install, Warning Install, Remote Management: Trust, Profile INstalled: DONE
	Gmail: Sign in, Turn on Caption, Done  
	Or second: Gmail Avatar Manage Accounts: Toggle On caption, Done 
	Device Policy Alert: OK. Then I get mail to approve. When approved GMail avatar Toggle ON. 
	Avatar to switch OR use all inbox
12: Android
	Go to Google Play Store
	Search for Google Device Policy
	Download/Enable/Open
	Add Account: Add Account
	Authenticate
	Enter email then next
	Enter password then next
	2FA Yes or enter 6 digit code then next
	I agree
	Delete Existing Profile
	Accept & continue
	(Setting up work profile) just wait it out.
	Data in your work Profile: click Next
	(Registering profile…)
	Device awaiting approval (I’ll do this on my end)
	Your Work Checklist: click: Install apps
	Installing work apps… click Next
13: After HIPAA Traning complete notification:
	Move user to appropriate OU
14: Close Onboarding Ticket in ITSD
15: When Signed Company Issued Equipment Agreement Form returns, go to Asset Panda
		Search for User
		Click Attachments in left pane
		Click Documents tab
		Click Add and upload document

