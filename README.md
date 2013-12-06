# Solo

Prevents two of the same cronjobs from running at the same. It is useful with cron to make sure that a job doesn't run before a previous one has finished.

This script is a port of the original [solo](http://timkay.com/solo/) bash script written by [Tim Kay](http://timkay.com/). It has been ported to PHP to make it available on Windows servers.

## Installation

Add the following to your composer.json.

    {
        "require": {
            "bashaus/solo": "dev-master"
        }
    }

## Usage

    bin/solo [port] [exec*]

- Argument `port` is an arbitrary port number to lock
- Argument `exec` is a shell command to run

You can use it with cron like this:

    * * * * * cd ...; bin/solo 24601 ./task.php arg1 arg2 arg3

The script task.php run every minute, but only if the previous invocation has finished. You can use any parameters, it doesn't have to run it every minute.

## Further reading

Take a look at Tim Kay's [documentation](http://timkay.com/solo/) for more use cases and how to use solo.

## Contributors

* [Tim Kay](http://www.timkay.com) - Original concept
* [Bashkim Isai](http://www.bashkim.com.au) - PHP port

If you fork this project and create a pull request add your GitHub username, your full name and website to the end of list above.

