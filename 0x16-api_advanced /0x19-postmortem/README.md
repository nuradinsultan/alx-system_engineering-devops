Solutions to 0x19. Postmortem
-Devops -Systems Administration

Issue Summary:
On August 10th, 2023, from 2🕙0 PM to 4:00 PM (WAT), our primecare api experienced a complete outage. The api became unresponsive, and users were unable to access the site during this time.

Impact:
The outage impacted all services provided by the website, including doctor page which patient listings, nurse and card room card functionality, and the checkout process. All users attempting to access the api were met with error messages or an unresponsive page. We estimate that approximately 80% of our users were affected by the outage.

Root Cause:
The root cause of the outage was a memory leak in our api server. The memory leak caused the server to become overloaded and unresponsive, resulting in the complete outage of the website.

Timeline:
2:00 PM - The issue was first detected by our monitoring system, which sent out an alert to the operations team.
2💯5 PM - The operations team attempted to restart the api application server, but this did not resolve the issue.
2:00 PM - The team began investigating the issue, assuming it was a problem with the server's configuration.
2:30 PM - Further investigation revealed that the server's memory usage was abnormally high, leading the team to suspect a memory leak.
3:00 PM - The team started looking into the application's code to identify any potential causes of the memory leak.
3:20 PM - The team identified the memory leak in the code and began working on a fix.
4:30 PM - The team deployed the fix and restarted the api application server.
4:45 PM - The website was back online and fully operational.
Misleading Investigation/Debugging Paths:
The team initially assumed that the issue was related to the server's configuration and spent valuable time investigating that angle. This delayed the identification of the actual root cause of the problem. Incident Escalation: The incident was initially handled by the operations team, but they escalated it to the development team once they realized the issue was related to the application's code.

Resolution:
The memory leak in the web application code was identified and fixed. The fix involved optimizing the code and implementing better memory management practices. The web application server was restarted after the fix was deployed, and the website was restored to full functionality.

Corrective and Preventative Measures:
To prevent similar issues in the future, we will implement the following corrective and preventative measures:

Perform regular code reviews to identify potential memory leaks.
Implement more rigorous testing procedures to catch memory leaks before they make it to production.
Implement more robust monitoring of server performance and resource usage.
Improve documentation and training for the operations team to better handle incidents like this in the future.
Specific tasks to address the issue include:
Conduct a comprehensive code review of the web application code.
Implement additional automated tests to detect memory leaks.
Update monitoring tools to include more granular resource usage data.
Provide additional training for operations team members on troubleshooting web application issues.
you can check out my blogpost on https://medium.com/@marameref
/0x19-postmortem-an-alx-software-engineering for more details
