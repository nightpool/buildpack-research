A buildpack to explore properties of the Heroku runtime.

Usage
-----

```bash
git init buildpack-research-app
cd buildpack-research-app
heroku create --buildpack https://github.com/mars/buildpack-research.git
echo "Empty app for buildpack research." > README.md
git add README.md
git commit -m "🚀"
git push heroku master

heroku logs -t
```

Example output
--------------

```
…heroku[api]: Deploy 58d1fdd by mars@heroku.com
…heroku[api]: Running release v5 commands by mars@heroku.com
…heroku[slug-compiler]: Slug compilation started
…heroku[slug-compiler]: Slug compilation finished
…heroku[release.9768]: Starting process with command `bin/echo_env`
…heroku[release.9768]: State changed from starting to up
…app[release.9768]: Running .profile.d/1.sh
…app[release.9768]: Running .profile.d/2.sh
…app[release.9768]: Running .profile.d/3.sh
…app[release.9768]: Running .profile.d/a.sh
…app[release.9768]: Running .profile.d/b.sh
…app[release.9768]: Running .profile.d/c.sh
…app[release.9768]: -----> Environment variables
…app[release.9768]:        HEROKU_SLUG_COMMIT=58d1fdd868e8f31143bda9a6671af5e732df1f44
…app[release.9768]:        HEROKU_APP_NAME=buildpack-research
…app[release.9768]:        I_AM_VARIABLE=true
…app[release.9768]:        HEROKU_RELEASE_CREATED_AT=2016-09-06T05:00:25Z
…app[release.9768]:        DYNO=release.9768
…app[release.9768]:        PATH=/usr/local/bin:/usr/bin:/bin
…app[release.9768]:        HEROKU_APP_ID=9b716fdd-b761-45cb-891a-f87779353659
…app[release.9768]:        PWD=/app
…app[release.9768]:        HEROKU_DYNO_ID=ebe46c2f-f85f-46e3-8eb0-acf0f793e4e4
…app[release.9768]:        HEROKU_RELEASE_VERSION=v5
…app[release.9768]:        HOME=/app
…app[release.9768]:        SHLVL=2
…app[release.9768]:        HEROKU_SLUG_DESCRIPTION=Deploy 58d1fdd
…app[release.9768]:        PORT=50076
…app[release.9768]:        _=/usr/bin/env
…heroku[release.9768]: Process exited with status 0
…heroku[release.9768]: State changed from up to complete
…heroku[api]: Release v5 created by mars@heroku.com
```