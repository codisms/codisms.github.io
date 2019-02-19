Last week in the Q&A session, it was mentioned that having a dev environment set up for immediate use would be ideal.  This would include language like Node, Go, and Python, at a minimum.  Maintaining an environment such as this can become a pain with various updates and having to deal with multiple version of things.

I described how I create an environment per project so that I can keep my projects separated and easily handle version issues.  I do this by having an AWS instance per project, but an alternative is to have a VM per project.  I also run everything in Ubuntu so that my environment more closely matches that which the project is likely to run on.  No more issues of “it works on my Mac but not on the server” (or vice versa).  Also, for you Windows people, you don’t have to start over or fight getting some tool to work.

This provides the following benefits:
- If you are diligent about it, projects get a dedicated instance.
- Since projects are separated, you’re less likely to deal with version collisave a Linux version.)

That last one is probably the most painful for most users.  However, it will make one a better developer as you’ll rely less on specific tools.  James and I are “do everything at the command line” developers (via tmux and vim), but I know that isn’t for most people.  Using a VM, you’ll retain a GUI to run tools in.  If you do want to go hardcore, there’s a repo for that...

Engineers are lazy folk and I’m no different.  If I have to do something too often I’ll write a darn script for it.  That includes building an environment from scratch.  Here are the repos to my configs:
- Various configuration files for Ubuntu: https://github.com/codisms/env-config
- tmux: https://github.com/codisms/tmux-config
- vim: https://github.com/codisms/vim-config

JW is well known for stealing my configs to update his so that tells you I’ve put thought into them.

Finally here’s the script I use for setting up a new dev environment: https://github.com/codisms/dev-env-setup

Literally, this script will take a base Ubuntu 16.04 or 18.x instance and turn it into my fully-configured dev environment in under 30 minutes and includes the following:
- Languages: Go, Node, Ruby, PHP, Python (2 and 3), Perl, gcc, g++, Java 8
- Servers: PostgreSQL, Apache2, Redis
- Tools: AWS CLI, certbot, git, mercurial, Subversion, bazaar

Think about how much time it would take you to get all of that installed on your Mac and you’ll appreciate just how much is ready for you.  James and I are good at jumping into new projects because we maintain an environment with these tools at our fingertips.  Learning the command line will be _invaluable_ in your career.

Also in the meeting I mentioned above, a suggestion came up about creating a VM that people could share.  Well, here it is: https://www.dropbox.com/s/lsjkrp15anfddcf/Ubuntu%2018.04.1.zip?dl=0

This is not a configured instance yet; it’s a base install of Ubuntu 18.04.  However, run `./setup.sh` and it’ll go through the installation process.  The script will ask for the `sudo` password (`cofebe`) and do the rest on its own.  After the reboot, copy your `.netrc` and SSH keys and you’re good to go.  You’ll probably want to do your own customizations, but this is a _very_ good start compared to zero.

If you want to get really fancy, we should talk about using Apache as a reverse proxy for your projects.  This may be required if you’re dealing that heavily depend on HTTPS but is also a really good skill to learn.

And there you have it.  If you ever look at my screen and you see a terminal window, that’s the environment I’m in.  I literally only do iOS development on my Mac.  It’s a good habit to get into and the above should get you started.

Please let me know if you have any questions.

