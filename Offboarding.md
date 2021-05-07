1: Ticket from ITSD with Departure Date
2: Add user to RBAC Matrix
	create row with depart date, and name
3: Adduser to Departing Employees tool in Code42
	https://console.us.code42.com/app/#/detection/departing-employees
##on end date or on hardware return##
4: Lock company owned devices in JAMF with random passcode, save in 1Password
5: In Gsuite
	Wipe data from approved devices
	After wipe, Delete Device
	Change User Password
	Click Security section
		Revoke security keys
		Remove Recovery phone and email
		Reset sign in cookies
		Remove app-specific passwords
		Remove connected applications
	Click Groups
		remove all groups
	Click Managed Devices
		remove all
	Click Shared drives
		remove all
	Move user to Former
	Determine if mail is Delegated/Routed
		This requires Ainsley's direct approval
		Screen shot the approval and attach it to the ticket
			Delegated: log in with changed password and backup code
				Grant access to manager/recipient
			Routing: Apps: Gmail: Advanced Settings: Routing: Add Another
	If no forward/routing/delegation Archive within 90days 
	Data Transfer: if requested, transfer to requesting party
6: In 1Password
	Find and suspend user account
7: In Duo
	Find and disable user
8: In Zoom.us
	Find and deactivate user
9: In Slack
	Find and deactivate user
10: In Microsoft
	Find user, revoke licenses
	Delete Account
11: In Adobe
	Find user, revoce licenses
	This may happen automatic with autoprovisioning
12: In Atlassian (covers Jira/Confluence)
	Find user, disable account
13: In Asset Panda
	set user to inactive
	Click Linked
		de-associate user with devices if returned
14: In Code42
	Find User
	Confirm user backup is 100%
	Block User
15: In CarbonBlack
	Find user's device
	Select device, uninstall sensors
	Select device, delete deregistered devices
16: In Kolide
	Find user's device
	Open device record
	Click Actions: Remove from Kolide
	Type the device name and confirm
17: In JAMF
	Find user's device
	rename by prepending a lower case x
	preserve the activation lock
18: In Trello
	at https://trello.com/captionhealth/members find and deactivate user
20: In RBAC
        Mark each column as Suspended/Doesn't Exist/Deleted per confirmation in above steps
        SysOps/DevOps/SecOps can be confidently handled by us
        SSO apps will disable with logoff, changed password, and CAA
        Unassign apps in Adobe (sign, dc, creative) change RBAC
        Unassign apps in Microsoft change RBAC
        Disable Zoom account change RBAC
        Disable Slack Account change RBAC
        Remind #on-off-boarding folks to check accounts 
21: If there is no legal hold and backup is good, get the Activation Lock from JAMF
	Power off the computer
	Power on the computer and immediately press and hold Option-Command-R
	The Globe will spin
	Select Disk Utility
	Delete Volume Group
	Delete Drive (rename it Macintosh HD)
	Quit Disk Utility
	Reinstall OS (the above keys with startup will restore most current OS)
	When asked for Country, press and hold power for 10 seconds
	Clean stickers, Clean Screen, Disinfect keys and case
	label the computer year, condition, and ready to enroll
