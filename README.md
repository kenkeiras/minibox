Minibox
=======

A minimalistic, libre, command line interface to the Dropbox API.

Requisites
==========

It depends on the following perl libraries (available through CPAN).

 * [Config::Tiny](http://search.cpan.org/~adamk/Config-Tiny-2.14/lib/Config/Tiny.pm)
 * [DateTime::Format::Strptime](http://search.cpan.org/~drolsky/DateTime-Format-Strptime-1.52/lib/DateTime/Format/Strptime.pm)
 * [WebService::Dropbox](http://search.cpan.org/~askadna/WebService-Dropbox-1.17/lib/WebService/Dropbox.pm)


Usage
=====

Setup
-----

Just create a *.mb.cnf* file with the following syntax on the target folder
(you may request it on the [Dropbox developers site](https://www.dropbox.com/developers/apps))

    KEY = <API key>
    SECRET = <API secret>

Do a general pull, it'll output a URL to grant access to your account:

    [~/dropbox]$ minibox pull
    Please Access URL and press Enter: https://www.dropbox.com/1/oauth/authorize?oauth_token=****************&oauth_callback= at minibox line 60.

Access it with a browser, grant it access and press enter on the minibox
terminal, an access token and secret with be displayed, copy it to the .mb.cnf
file in order to not having to repeat this process:

    ACCESS_TOKEN = <displayed access token>
    ACCESS_SECRET = <displayed access secret>


I/O
---

Pull files and directories from Dropbox, if no one is specified it defaults to
the Dropbox folder root.

    minibox pull [<file/directory> [<file/directory> [...]]]

Push files and directories from Dropbox, if no one is specified it defaults to
the Dropbox folder root.

    minibox push [<file/directory> [<file/directory> [...]]]
