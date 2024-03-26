## Cron job

    30 08 * * * /home/pete/scripts/change_wallpaper
    The fields are as follows from left to right:

  Minute - (0-59)
  Hour - (0-23)
  Day of the month - (1-31)
  Month - (1-12)
  Day of the week - (0-7). 0 and 7 are denoted as Sunday
  The asterisk in the field means to match every value. 
  So in my above example, I want this to run every day in every month at 8:30am.

To create a cronjob, just edit the crontab file:

crontab -e
