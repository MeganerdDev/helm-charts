# Initialization Job as Helm Hook

!!! warning
    Only enable this once Nautobot has been deployed 1 time or if you are using an external database.  If the database has never been populated the deployments will fail to start and this job to populate the database will never run.

In certain deployments where shared storage is used for Nautobot static and media files such as [using S3 for Django storage](https://docs.nautobot.com/projects/core/en/stable/user-guides/s3-django-storage) (see the Nautobot [examples](https://github.com/nautobot/nautobot/tree/develop/examples/s3_static_files) for configuring Nautobot) it is not necessary for EVERY pod to run all of the Nautobot post-init tasks.  These take a significant amount of time, and offloading them onto a separate single execution Kubernetes Job can greatly improve the pod restart speeds.  This can simply be accomplished by setting:

```yaml
nautobot:
  singleInit: true
```

!!! note
    The specs for the job default to the values specified in the `.nautobot` values, if you would like to override them any value in `.nautobot` can also be specified in `.initJob`
