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

### Build

```
git push heroku master
Counting objects: 1, done.
Writing objects: 100% (1/1), 191 bytes | 0 bytes/s, done.
Total 1 (delta 0), reused 0 (delta 0)
remote: Compressing source files... done.
remote: Building source:
remote: 
remote: -----> Research 🔬 app detected
remote: -----> ENV_DIR
remote:        total 36K
remote:        drwx------ 2 u42856 dyno 4.0K Sep  6 05:00 .
remote:        drwx------ 5 u42856 dyno 4.0K Sep  6 05:00 ..
remote:        -rw------- 1 u42856 dyno   36 Sep  6 05:00 HEROKU_APP_ID
remote:        -rw------- 1 u42856 dyno   18 Sep  6 05:00 HEROKU_APP_NAME
remote:        -rw------- 1 u42856 dyno   20 Sep  6 05:00 HEROKU_RELEASE_CREATED_AT
remote:        -rw------- 1 u42856 dyno    2 Sep  6 05:00 HEROKU_RELEASE_VERSIO
remote:        -rw------- 1 u42856 dyno   40 Sep  6 05:00 HEROKU_SLUG_COMMIT
remote:        -rw------- 1 u42856 dyno   14 Sep  6 05:00 HEROKU_SLUG_DESCRIPTION
remote:        -rw------- 1 u42856 dyno    4 Sep  6 05:00 I_AM_VARIABLE
remote: -----> Environment variables
remote:        HEROKU_APP_ID=9b716fdd-b761-45cb-891a-f87779353659
remote:        HEROKU_APP_NAME=buildpack-research
remote:        HEROKU_RELEASE_CREATED_AT=2016-08-15T22:52:37Z
remote:        HEROKU_RELEASE_VERSION=v4
remote:        HEROKU_SLUG_COMMIT=a24b0c07938f5d80ccd8a7f40cf8b5f2c43ba2ac
remote:        HEROKU_SLUG_DESCRIPTION=Deploy a24b0c0
remote:        I_AM_VARIABLE=true
remote: -----> Release-phase setup
remote: -----> .profile.d/ setup
remote: -----> Discovering process types
remote:        Procfile declares types     -> (none)
remote:        Default types for buildpack -> release
remote: 
remote: -----> Compressing...
remote:        Done: 646B
remote: -----> Launching...
remote:  !     Release command declared: this new release will not be available until the command succeeds.
remote:        Released v5
remote:        https://buildpack-research.herokuapp.com/ deployed to Heroku
remote: 
remote: Verifying deploy... done.
remote: Running release command.... done.
To https://git.heroku.com/buildpack-research.git
   a24b0c0..58d1fdd  master -> master
```

### Runtime

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