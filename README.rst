pelican.vim
=============

Pelican.vim_ is intended to automate the process of creating and editing
Pelican_ blog posts from within Vim_.

.. _vim: http://www.vim.org
.. _pelican.vim : http://github.com/edthedev/pelican.vim
.. _Pelican: http://getpelican.com

This started as a complete rewrite of jekyll.vim_ for the Pelican crowd. Also see vim-octopress_ for further inspirations.

.. _jekyll.vim: https://github.com/csexton/jekyll.vim
.. _vim-octopress: https://github.com/tangledhelix/vim-octopress

Install 
-----------------------------
This plugin is packaged for use with Vundle_.

.. _Vim: http://vim.org/about.php
.. _Python: http://python.org
.. _Vundle: https://github.com/gmarik/vundle/blob/master/README.md 

Install Vundle_ and then add 'edthedev/pelican.vim' to your .vimrc.::

    Bundle 'edthedev/pelican.vim'

Then, from within Vim, run BundleInstall.::

    :BundleInstall

Configure
-----------------------------

Pelican.vim needs to know where your blog source files will be stored.::

    let g:pelican_blog_source = ~/blog_source_files

Pelican.vim also needs to know where you would like the generated HTML files to be placed (locally).::

    let g:pelican_blog_html = ~/blog_html_destination

If you store your blog source files in a Git repository, let Pelican.vim manage commits for you::

    let g:pelican_git_master = http://github.com/username/blog.git

If you publish your Pelican_ blog over SSH, tell Pelican.vim the destination location, and it can run a publish command for you::

    let g:pelican_publish_server = username@server.domain.com:~/public_html_directory

Altogether, the directives added to your ``~/.vimrc`` should looke a bit like::

    Bundle 'edthedev/pelican.vim'
    let g:pelican_blog_source = ~/blog_source_files
    let g:pelican_blog_html = ~/blog_html_destination
    let g:pelican_git_master = http://github.com/username/blog.git
    let g:pelican_publish_server = username@server.domain.com:~/public_html_directory

Commands
---------

Clone your Pelican blog source files from your Git repository::

    :call pelican#pull()

Make some changes::

    TODO: Command to open your source folder.

Commit and push your changes back to your Git repository.::

    :call pelican#commit()

Generate your blog HTML. This command requires that pelican.conf.py and a 'content' folder exist in g:pelican_blog_source folder.::

    :call pelican#rst2html()

Publish your updated HTML content, using Rsync_, to your remote web server::

    :call pelican#publish()

.. _Rsync: http://rsync.samba.org/ 

License
---------

Same as Vim itself, see ``:help license``.
