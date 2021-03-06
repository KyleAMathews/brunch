Command line API
================

``brunch new <rootPath>``
-------------------------
Create new brunch project. Options:

* ``rootPath``: (required) name of project directory that would be created
* ``-s PATH_TO_SKELETON, --skeleton PATH_TO_SKELETON``: path or
git repo address of project, contents of which will be copied to new dir.

`.git` directory is automatically removed when copying.

Short-cut: ``brunch n``.

Examples:

* ``brunch n twitter -s ~/brunch-templates/simple``
* ``brunch n twitter -s git://github.com/paulmillr/brunch-with-chaplin.git``

``brunch build``
----------------
Build a brunch project. Options:

* ``-m, --minify``: minify the result js & css files? Analog of ``minify`` option in config file.
* ``-c CONFIG_PATH, --config CONFIG_PATH``: path to config (default: ``config``)

Short-cut: ``brunch b``.

Examples:

* ``brunch b -c ios_config -m``: would load ios_config.(js,coffee), build application and minify the output.

``brunch watch``
----------------
Watch brunch directory and rebuild if something changed. Options:

* ``-s, --server``: run a simple http server that would server `output` dir
* ``-p PORT, --port PORT``: if a `server` option was specified, define on which port the server would run
* ``-c CONFIG_PATH, --config CONFIG_PATH``: path to config (default: ``config``)
* ``-m, --minify``: minify the result js & css files? Analog of ``minify`` option in config file.

Short-cut: ``brunch w``.

Examples:

* ``brunch w``: simply watch current directory &amp; compile the output to ``build`` directory.
* ``brunch w -s``: watch current project and run a webserver that would work on ``public`` directory (by default).
* ``brunch w -s -p 8841 -m``: watch current project and run a webserver that would work on ``public`` directory (by default). Also, auto-minify files.

``brunch generate <type> <name>``
---------------------------------
Generate model, view or route for current project. Options:

* ``type``: (required) generator type. One of: collection, model, router, style, template, view.
* ``name``: (required) generator class name / filename.
* ``-p PATH_TO_DIRECTORY --path PATH_TO_DIRECTORY``: path to directory in which file will be created. Useful if you prefer non-standard directory structure.

Short-cut: ``brunch g``.

Examples: 

* ``brunch generate collection user_list``: would generate file ``app/collections/user_list.coffee`` with class ``UserList`` and a unit-test ``test/unit/collections/user_list.coffee``.
* ``brunch g model post -p app/twitter/models``: would generate file ``app/twitter/models/post.coffee`` with class ``Post`` and a unit-test ``test/unit/twitter/models/post.coffee``.

``brunch destroy <type> <name>``
--------------------------------
Destroy model, view or route for current project, created by `brunch generate`. Options:

* ``type``: (required) generator type. One of: collection, model, router, style, template, view.
* ``name``: (required) generator class name / filename.
* ``-p PATH_TO_DIRECTORY --path PATH_TO_DIRECTORY``: path to directory in which file will be deleted. Useful if you prefer non-standard directory structure.

Short-cut: ``brunch d``.

Examples: 

* ``brunch destroy collection user_list``: would remove file ``app/collections/user_list.coffee`` with class ``UserList`` and a unit-test ``test/unit/collections/user_list.coffee``.
* ``brunch d model post -p app/twitter/models``: would remove file ``app/twitter/models/post.coffee`` with class ``Post`` and a unit-test ``test/unit/twitter/models/post.coffee``.
