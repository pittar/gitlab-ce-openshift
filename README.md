# GitLab CE 12 on OpenShift 4

First cut at GitLab on OpenShift.

Based on [Red Hat CoP GitLab SSL template](https://github.com/redhat-cop/containers-quickstarts/blob/master/gitlab-ce/.openshift/templates/gitlab-ssl.yml), but SSL passthrough removed in favour of route "edge" TLS termination.  The version has also been bumped to GitLab 12.10.14.

## To Install

1. Fork, then clone this repository.
2. Update the following:
    * In `gitlab-route.yaml`, update the `host` to `gitlab.<your apps wildard route>`
    * In `gitlab-dc.yaaml`, updaate the `external_url` value in the `GITHUB_OMNIBUS_CONFIG` to match your route url `https://gitlab.<your apps wildard url>/`
3. `oc apply -k <repository path>`