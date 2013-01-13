kit_app - A sample app instance of the Kit CMS
=======

A simple application using DSC's Kit CMS engine to provide a complete, highly functional community web site.  In fact, the app
itself contains no functionality whatsoever; the complete CMS including WYSIWYG in place editing, forums, asset management,
etc. is all provided by the Kit Rails engine.  However this app is still useful as the fastest way to get up and running because 
most of the installation steps have been precompleted.  If you're comfortable building Rails app you're probably better off
starting with the [kit_cms gem itself](https://github.com/dsc-os/kit_cms).

Installation
------------

(These instructions assume you're using a Unix-like OS.  It should all work on Windows too, but installation might need tweaking. They also assume you've a recent version of MySQL, git, rubygems, bundler installed.  If not, install those first.)

    git clone git://github.com/dsc-os/kit_app.git
    cd kit_app
    bundle
    rake db:create
    rake db:schema:load
    rake db:data:load
    vendor/es/bin/elasticsearch
    rails s thin
    
Now visit (http://localhost:3000)[http://localhost:3000].  The default admin email is "demo@dsc.net" and password "demodemo".  Optionally, to change the default admin email do:

    rails dbconsole
    update users set email = 'YOUREMAIL@YOURDOMAIN' where email = 'demo@demo.com';
    exit
    



    
