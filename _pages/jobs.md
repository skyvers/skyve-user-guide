---
title: "Jobs"
permalink: /jobs/
excerpt: "Creating and configuring jobs within a Skyve application."
toc: true
sidebar:
  title: "Index"
  nav: docs
---
 
Jobs within a Skyve application allow long running tasks (jobs) to be scheduled to run in the background. Jobs can be scheduled to be run once, or a schedule can be saved if they need to run repeatedly over time, e.g. a nightly backup job.

## Scheduling a recurring job

1. Under the 'Admin' module, click into 'Jobs'
![Jobs Menu]({{ site.url }}{{ site.baseurl }}/assets/images/Jobs1.PNG)

2. Navigate into the 'Schedule' tab
![Jobs Schedule]({{ site.url }}{{ site.baseurl }}/assets/images/Jobs2.PNG)

3. Click '+' to add a new job
![Jobs Adding]({{ site.url }}{{ site.baseurl }}/assets/images/Jobs3.PNG)

4. Enter the job to be run in 'Job To Run' and the user to run it as in 'Run As'
![Jobs Run]({{ site.url }}{{ site.baseurl }}/assets/images/Jobs4.PNG)

5. Enter the time you want the job to run, as well as the days/dates it should run 
- If the job should run always, select the 'All' buttons to indicate that the job should run during every time or date period
- If the job should run at chosen times/dates, select the 'Selected' button and click the times/dates that the job should run
- A combination of these 'All' and 'Selected' times and dates can be utilised to gain the required job times
![Jobs Dates]({{ site.url }}{{ site.baseurl }}/assets/images/Jobs5.PNG)

6. (optional). A date range for the job to run can be applied at the bottom of the page
![Jobs Menu]({{ site.url }}{{ site.baseurl }}/assets/images/Jobs6.PNG)

7. Click 'OK' to save and return


## Scheduling a one-off job

1. Under the 'Admin' module, click into 'Jobs'
![Jobs Menu]({{ site.url }}{{ site.baseurl }}/assets/images/Jobs1.PNG)

2. Navigate into the 'Schedule' tab
![Jobs Schedule]({{ site.url }}{{ site.baseurl }}/assets/images/Jobs2.PNG)

3. Click '+' to add a new job
![Jobs Adding]({{ site.url }}{{ site.baseurl }}/assets/images/Jobs3.PNG)

4. Enter the job to be run in 'Job To Run' and the user to run it as in 'Run As'
![Jobs Run]({{ site.url }}{{ site.baseurl }}/assets/images/Jobs4.PNG)

5. If the job is a one off, click 'Schedule Job for Now'

6. Click 'Cancel', then check 'Completed Jobs' under the 'Actual' tab

7. Click 'OK' to save and return
