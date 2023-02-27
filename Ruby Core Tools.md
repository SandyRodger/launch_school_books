[Core Ruby Tools](https://launchschool.com/books/core_ruby_tools)

 ### [Introduction](https://launchschool.com/books/core_ruby_tools/read/introduction)
 
Ruby tools:

- RubyGems
- Rbenv / RVM
- Bundler
- Rubocop
- databases
- SQL
- Rake
- Rails

 It's a lot, but it's also what makes Ruby so handy.
 
 ## [Your Ruby Installation](https://launchschool.com/books/core_ruby_tools/read/your_ruby_installation)
 
 - Most systems come with Ruby pre-installed.
 
 How did Ruby get on my system?
 
  #### On Cloud9
  It uses pre-built work-spaces, based on standard Linux distributions. It automatically installs the RVM Ruby Version Manager. 
  RVM allows one to manage Ruby components without root privileges, which is safer for the user. Cloud9 is the easiest way  to install Ruby.
  #### On a Mac
  - Ruby is part of the standard OS X/macOS installation. Find the ruby command at `/usr/bin/ruby`. This is your "system ruby".
  `/usr/bin/ruby -v` tells you which version you're using. 
  - Undesireably, Mac system Ruby needs root access to install and manipulate other Ruby components. Root access isn't always available to the developer, so this can be a ball-ache.
  - So it's outdated and denies you full access, this is why you should install a Ruby Version Manager and use it to install the "Rubies" you need. 
  - You can do this by installing homebrew, which is a package manager designed for Macs.
  ### On Linux
  - If Ruby is not already installed you can install it with your package manager (RPM, Yum, DPKG) and it will end up in the `/usr/bin` and `/usr/lib/ruby` directories.
  
  ## [What Ruby am I running?](https://launchschool.com/books/core_ruby_tools/read/your_ruby_installation)
   - `which ruby` tells you where ruby is. Mine is `/usr/bin/ruby`, which is the pre-installed Mac version, and not good enough. 
   - I need to install a Ruby Version Manager later.
   - The system Ruby also stores additional commands, like `irb` and `rake` in the same directory.
   - `usr/bin/ruby` contains other Ruby libraries and gems, but actually it's an alias for the real directories, nestled more deeply in `/System/Library/Frameworks`, which is a place you should never modify directly.
   - other responses to `which ruby` are: 
     - `/usr/local/rbenv/shims/ruby`
     - `/usr/local/rvm/rubies/ruby-2.2.2/bin/ruby`
    
   - `ruby -v` tells you which version of ruby you have installed. 
   - The latest version of Ruby can be seen [here](https://www.ruby-lang.org/en/downloads/)
   
   
  
