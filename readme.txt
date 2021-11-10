本项目来自Adminer，Adminer自4.6.3版本起不再支持无密码登录数据库，导致使用sqlite等无密码的文件数据库很是麻烦，经过仔细核对，只需要修改Adminer项目的~\adminer\include\adminer.inc.php文件中的一行代码即可正常使用。
原来的代码
```
	function credentials() {
		return array(SERVER, $_GET["username"], get_password());
	}
```
改动后的代码
```
	function credentials() {
		return array(SERVER, '', '');
	}
```
最后使用compile.php编译成一个单文件就可以直接使用了

Adminer - Database management in a single PHP file
Adminer Editor - Data manipulation for end-users

https://www.adminer.org/
Supports: MySQL, MariaDB, PostgreSQL, SQLite, MS SQL, Oracle, Elasticsearch, MongoDB, SimpleDB (plugin), Firebird (plugin), ClickHouse (plugin)
Requirements: PHP 5+
Apache License 2.0 or GPL 2

adminer/index.php - Run development version of Adminer
editor/index.php - Run development version of Adminer Editor
editor/example.php - Example customization
plugins/readme.txt - Plugins for Adminer and Adminer Editor
adminer/plugin.php - Plugin demo
adminer/sqlite.php - Development version of Adminer with SQLite allowed
editor/sqlite.php - Development version of Editor with SQLite allowed
adminer/designs.php - Development version of Adminer with adminer.css switcher
compile.php - Create a single file version
lang.php - Update translations
tests/katalon.html - Katalon Automation Recorder test suite

If downloaded from Git then run: git submodule update --init
