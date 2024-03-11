# Bitbucket Cheet Sheet

## Check Bitbucket service user context

```
systemctl status bitbucket | grep 'Main PID'
ps -o user= -p <PID>
```

# Bitbucket Password recovery (Lockout recovery process)

[Lockout recovery process](https://confluence.atlassian.com/bitbucketserver/lockout-recovery-process-776640158.html)

```
vi /opt/atlassian/bitbucket/current/bin/_start-webapp.sh
# Uncomment JVM_SUPPORT_RECOMMENDED_ARGS and set it as below
JVM_SUPPORT_RECOMMENDED_ARGS=-Datlassian.recovery.password=temporarypassword
# Restart bitbucket service with systemctl restart bitbucket
# Login using recvery_admin user name and temporarypassword as a password value
```

