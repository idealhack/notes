# GitLab

## Overview

- [The only single product for the complete DevOps lifecycle - GitLab | GitLab](https://about.gitlab.com/)

## Install

[Installation methods for GitLab | GitLab](https://about.gitlab.com/installation/)

### On CentOS

- [Installing GitLab on Google Cloud Platform | GitLab](https://docs.gitlab.com/ee/install/google_cloud_platform/index.html)
- [Installation methods for GitLab | GitLab](https://about.gitlab.com/installation/#centos-7)

### On Kubernetes

- [Installing GitLab on Kubernetes | GitLab](https://docs.gitlab.com/ce/install/kubernetes/)

    helm upgrade --install gitlab gitlab/gitlab \
      --timeout 600 \
      --set global.hosts.domain=demo-gitlab.idealhack.com \
      --set global.hosts.externalIP=35.189.157.39 \
      --set certmanager-issuer.email=idealhack@gmail.com \
      --set gitlab.migrations.image.repository=registry.gitlab.com/gitlab-org/build/cng/gitlab-rails-ce \
      --set gitlab.sidekiq.image.repository=registry.gitlab.com/gitlab-org/build/cng/gitlab-sidekiq-ce \
      --set gitlab.unicorn.image.repository=registry.gitlab.com/gitlab-org/build/cng/gitlab-unicorn-ce
