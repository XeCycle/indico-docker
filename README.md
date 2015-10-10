# docker-compose based Indico installation

First of all please not that this installation is not in any way supported
by CERN.

To use, clone this repo or grab a tarball at the
[releases page](https://github.com/XeCycle/indico-docker/releases), then
copy `indico.env.sample` to `indico.env` and customize it, and finally
`docker-compose up -d`.  You have to wait for database initialization to
finish before accessing the page.

## Known problems

Not all features are tested, and the following are known to be broken:

- Not all configuration options are exposed in `indico.env`
- No support for database upgrading (I have no idea how that works)
