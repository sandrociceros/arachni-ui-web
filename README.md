# Experimental/unstable branch -- used for development/integration

This branch is where all development takes place, once its code has been tested and
is considered stable, it is then merged into the `master` branch and released.

## Nightlies

For self-contained, nightly snapshot packages take a look at:
http://downloads.arachni-scanner.com/nightlies/

## Source

To run from source you first need to setup a
[development environment](https://github.com/Arachni/arachni/wiki/Development-environment).

    git clone https://github.com/Arachni/arachni-ui-web
    cd arachni-ui-web

    # --binstubs will make the executables of the Framework available under 'bin/',
    # so that you'll be able to run the CLI if needed.
    bundle install --binstubs

    rake db:migrate
    rake db:setup
    script/rails s thin

For seed data (default user accounts etc) take a look in `db/seeds.rb`.

Also, the DB schema is pretty fluid during development so migrate after each
`git pull` and don't be surprised if you'll have to remove the existing schema
and DBs for things to work again:

    rm db/development.sqlite3
    rm db/test.sqlite3
    rm db/schema.rb
    rake db:migrate
    rake db:setup

# Arachni - Web User Interface

<table>
    <tr>
        <th>Version</th>
        <td>0.4dev</td>
    </tr>
    <tr>
        <th>Homepage</th>
        <td><a href="http://arachni-scanner.com">http://arachni-scanner.com</a></td>
    </tr>
    <tr>
        <th>Blog</th>
        <td><a href="http://arachni-scanner.com/blog">http://arachni-scanner.com/blog</a></td>
    <tr>
        <th>Github</th>
        <td><a href="http://github.com/Arachni/arachni-ui-web">http://github.com/Arachni/arachni-ui-web</a></td>
     <tr/>
    <tr>
        <th>Documentation</th>
        <td><a href="https://github.com/Arachni/arachni-ui-web/wiki">https://github.com/Arachni/arachni-ui-web/wiki</a></td>
    </tr>
    <tr>
        <th>Support</th>
        <td><a href="http://support.arachni-scanner.com">http://support.arachni-scanner.com</a></td>
    </tr>
    <tr>
       <th>Author</th>
       <td><a href="mailto:tasos.laskos@gmail.com">Tasos Laskos</a> (<a href="http://twitter.com/Zap0tek">@Zap0tek</a>)</td>
    </tr>
    <tr>
        <th>Twitter</th>
        <td><a href="http://twitter.com/ArachniScanner">@ArachniScanner</a></td>
    </tr>
    <tr>
        <th>Copyright</th>
        <td>2013 Tasos Laskos</td>
    </tr>
    <tr>
        <th>License</th>
        <td><a href="file.LICENSE.html">Apache License Version 2.0</a></td>
    </tr>
</table>

![Arachni logo](http://arachni.github.com/arachni/logo.png)

## Synopsis

A web user interface and collaboration platform for the
[Arachni](https://github.com/Arachni/arachni) open source web application
security scanner framework.

## Features

 - Administrators can manage all:
    - Users
    - Scan configuration Profiles
        - Can set Global Profiles which are available to everyone.
        - Can set the system-wide default Profile.
    - Scans
    - Scan Issues
    - Scan Groups
    - Dispatchers
        - Can set Global Dispatchers which are available to everyone.
        - Can set the system-wide default Dispatcher.
    - Settings
        - Scan
            - Allowed types.
            - Target whitelist using regular expressions.
            - Target blacklist using regular expressions.
            - Global scan limit -- Amount of active scans at any given time.
            - Per scan limit -- Amount of active scans at any given time per user.
        - Profile
            - Allowed modules.
 - Users can:
    - Manage, create and share Dispatchers with each other.
    - Manage, create and share Scan configuration Profiles with each other.
    - Start Scans using one of the available Profiles (and optionally Dispatchers).
    - Organize Scans into Scan Groups for easier management and share their Groups with each other.
    - Manage, comment, share and export reports of their Scans.
    - Discuss and Review Issues:
        - Mark them as false positives
        - Mark them as fixed
        - Mark them as requiring manual verification
            - Add verification steps
            - Mark them as verified
    - Receive Notifications for:
        - Shared Profiles -- Created, updated, shared, deleted.
        - Shared Scans -- Started, paused, resumed, aborted, commented.
        - Issues of shared Scans -- Reviewed, verified, commented.
    - Review their Activity.
    - Export reports, review and comment on Scans which have been shared with them by other users.
 - Available Scan types:
    - Direct -- From the WebUI machine to the webapp, no need to setup anything else.
    - Remote -- Using a Dispatcher.
        - Scan is performed from the machine of the Dispatcher to the webapp.
        - Scan assignments can be load balanced when there are multiple Dispatchers available.
    - Grid -- Using multiple Dispatchers.
        - Scan is performed using multiple machines for a super-fast crawl and audit.
        - Scan assignments can be load balanced.
    - Repeat/Revision
        - Repeats a finished scan to identify fixed or new issues.
        - Can use sitemaps of previous revisions to:
            - Avoid crawling
            - Extend a new crawl
    - Overview -- Combines the results of multiple revisions for easy review/management.
 - Scan reports can be exported in multiple formats (HTML, XML, YAML and more).
 - Simple, clean, responsive design suitable for desktops, tablets and mobile phones.

## [Usage](https://github.com/Arachni/arachni-ui-web/wiki)

## Bug reports/Feature requests

Submit bugs using [GitHub Issues](http://github.com/Arachni/arachni-ui-web/issues)
and get support via the [Support Portal](http://support.arachni-scanner.com).

## Contributing

If you make improvements to this application, please share with others.

* [Fork the project](https://github.com/Arachni/arachni-ui-web/fork_select).
* Start a feature branch based on the `experimental` branch (`git checkout -b <feature-name> experimental`).
* Add specs for your code.
* Run the spec suite to make sure you didn't break anything (`rake spec`).
* Commit and push your changes.
* Issue a pull request and wait for your code to be reviewed.

_PS. You may want to setup a [development environment](https://github.com/Arachni/arachni/wiki/Development-environment) first._

## License

Arachni WebUI is licensed under the Apache License Version 2.0.<br/>
See the [LICENSE](file.LICENSE.html) file for more information.

## Disclaimer

This is free software and you are allowed to use it as you see fit.
However, neither the development team nor any of our contributors can held
responsible for your actions or for any damage caused by the use of this software.
