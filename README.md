## fail_mail

Wraps your scripts and emails you when they fail.  Useful for cron.

### example

Your cron used to be this:
```
MAILTO=sfritz@example.com
0 2 * * 1-5 ruby example.rb
```

Change to this:
```
0 2 * * 1-5 ./fail_mail 'ruby example.rb' --from cron --to sfritz@example.com --subject 'Example Job Failed!'
```

Now you only get bothered when the job has a non-zero exit status.  Sends stdout and stderr in the body.

FROM: cron@jobbox  
TO:   sfritz@example.com  
SUBJECT:  Example Job Failed!  

Everything was going fine until...  
...Something went wrong!



