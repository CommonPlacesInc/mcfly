# What it does #
Propels Drupal 6 sites into the Future by suppressing PHP strict warnings created when running a Drupal 6 site on PHP 5.4. 

If you've transferred a Drupal 6 site to a server running PHP 5.4 chances are pretty good that you'll see tons of errors 
flooding your watchdog logs and displaying on-screen messages from contributed modules. Some of these will eventually be 
fixed by maintainers but some inevitably will not. Sure you can fix your own code but what about all the others? 
What to do? You have a few options:

1.) Maybe you've switched your Drupal error reporting to be "log only". That's fine but expect your watchdog table to
balloon in size very quickly and you're probably noticing a significant performance lag.

2.) Maybe you tried to turn off strict warnings via settings.php, php.ini or .htaccess. None of those will work because
Drupal's drupal_error_handler function will override those settings unless you set the value to 0 (no error reporting
at all) which is not a good thing either.

3.) You could hack core, kill a kitten and move on. It would work, but what about the kitten?!

4.) Install this module which will gracefully override drupal_error_handler() with a slightly modified version which 
will suppress the warnings from being shown on the screen or added to the logs. No patches, no hacks, no killed kittens.w

