[![](https://images.microbadger.com/badges/image/gitlab/dind.svg)](http://microbadger.com/images/gitlab/dind "Get your own image badge on microbadger.com")

The `gitlab/dind` image can be used in place of `docker:dind` to build projects with docker-based workflow.

For example you can [register a gitlab-ci-multi-runner](http://docs.gitlab.com/ce/ci/docker/using_docker_build.html#use-docker-in-docker-executor) as Docker-in-Docker using this image like:

    sudo gitlab-ci-multi-runner register -n \
      --url https://gitlab.com/ci \
      --registration-token REGISTRATION_TOKEN \
      --executor docker \
      --description "My Docker Runner" \
      --docker-image "gitlab/dind:latest" \
      --docker-privileged

It contains:

  - The `docker` working as Docker-in-Docker similar to the official [docker:dind](https://hub.docker.com/_/docker/)
  - [`docker-compose`](https://docs.docker.com/compose/) (currently not in `docker:dind`).
