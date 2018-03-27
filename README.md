# gitlab-ce-subgit

Image: [squarebracket/gitlab-ce-subgit](https://hub.docker.com/r/squarebracket/gitlab-ce-subgit/)

[GitLab](http://gitlab.org)'s Community Edition, with [SubGit](http://www.subgit.com) v3.3.0 installed.

All of [GitLab's Docker-related documentation](http://doc.gitlab.com/omnibus/docker/) remains valid; the only differences compared to the [official Docker image(s)](https://hub.docker.com/r/gitlab/gitlab-ce/) provided by GitLabHQ are additions overtop of their images. This image contains an installation of SubGit, a tool for migrating and even mirroring subversion and git source code repositories, along with an additional volume for its configuration files.

[Subgit's SVN to Gitlab Howto](http://www.subgit.com/gitlab.html) is a worthwhile read.

## Volumes

`/etc/gitlab`: Configuration of the GitLab server

`/var/opt/gitlab`: Repositories

`/var/log/gitlab`: Logfiles

`/etc/subgit`: Location for subgit.key (if available; SubGit will find it there)

`/etc/cron.d`: Location for cron jobs (e.g., backups; see below)

## Usage

For GitLab itself, see http://doc.gitlab.com/omnibus/docker/.

For SubGit and Gitlab, see http://www.subgit.com/gitlab.html.

In contrast to the original image, the cron daemon is also launched when starting up GitLab. This allows processing of cron jobs added to /etc/cron.d. 

## Related

Bertrand Roussel provides at standalone Docker image ([corfr/subgit](https://registry.hub.docker.com/u/corfr/subgit/) | [Github](https://github.com/CoRfr/docker-subgit)) for an alternative approach to use SubGit with (in fact any) dockerized git repository servers.
