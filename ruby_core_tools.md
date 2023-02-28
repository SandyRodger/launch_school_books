# [Core Ruby Tools](https://launchschool.com/books/core_ruby_tools)

 ### [Introduction](https://launchschool.com/books/core_ruby_tools/read/introduction)
 
Some Ruby tools we'll cover or have covered:

- RubyGems
- Rbenv / RVM
- Bundler
- Rubocop
- databases
- SQL
- Rake
- Rails

 It's a lot, but it's also what makes Ruby so handy. This book is about learning how to navigate through your coding environment and potentially debug problems. These are not univeral coding concepts that require mastery.
 
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
  - You can do this by installing [homebrew](https://docs.brew.sh/), which is a package manager designed for Macs.
  #### On Linux
  - If Ruby is not already installed you can install it with your package manager (RPM, Yum, DPKG) and it will end up in the `/usr/bin` and `/usr/lib/ruby` directories.
  
  ### [What Ruby am I running?](https://launchschool.com/books/core_ruby_tools/read/your_ruby_installation)
   - `which ruby` tells you where ruby is. Mine is `/usr/bin/ruby`, which is the pre-installed Mac version, and not good enough. 
  - If `which ruby` has rbenv in it, you are using a bersion installed by rbenv. Ditto for RVM.
   - I need to install a Ruby Version Manager later.
   - The system Ruby also stores additional commands, like `irb` and `rake` in the same directory.
   - `usr/bin/ruby` contains other Ruby libraries and gems, but actually it's an alias for the real directories, nestled more deeply in `/System/Library/Frameworks`, which is a place you should never modify directly.
   - other responses to `which ruby` are: 
     - `/usr/local/rbenv/shims/ruby`
     - `/usr/local/rvm/rubies/ruby-2.2.2/bin/ruby`
    
   - `ruby -v` tells you which version of ruby you have installed. 
   - The latest version of Ruby can be seen [here](https://www.ruby-lang.org/en/downloads/)
   
   ### What gets installed with Ruby? 
   
    - The core library
    - The standard library
    - The `irb` REPL
   - The rake utility (a tool to automate Ruby dev tasks)
    - The gem command (a tool to manage Ruby Gems)
    - Documentation tools (`rdoc` and `ri`)
  
  ## [Gems](https://launchschool.com/books/core_ruby_tools/read/gems)
  
  ### What are Gems?
  
  - Packages of code that you can download, install and use in your Ruby program or from the command line.
  - `gem` manages your gems.
  - A list of gem commands can be found [here](http://guides.rubygems.org/command-reference/)
  - There are thousands of gems. Here are some we have already encountered:
    - `rubocop`
    - `pry`
    - `sequel` ? nope
    - `rails` ? not yet!

### Gems, Ruby and your Computer

 #### The Remote library
 - You can find gems in the [ruby  gems library](https://rubygems.org/gems) or you can search that library with a specialized remote library.
 - Install your gem with `gem install gem_name`. You can specify additional remote libraries to connect to your gem.
 #### The local library
 - When `gem` installs a gem it saves its files in your local library.
 - Where gem creates this local library depends on a few things (whether you are using a system Ruby that needs root access, a user maintainable Ruby, the specific Ruby version number and whether you use a Ruby versioin manager like RVM or Rbenv. `gem` knows where to put things and gets on with it.
 #### Gems and your File System
 - Sometimes you may want to look at a gem's source code. Maybe to understand how the gem works, or diagnose a problem with a gem not working.
 - Source code is available online, but if you have no connection you cna look in your computer.
 - Do not change the source code of your gem. It may cause unexpected behaviours and changes will be lost at the next update.
 - You can find where gems are being put by calling `gem env`. For me this prints the following:

```ruby 
RubyGems Environment:
  - RUBYGEMS VERSION: 3.2.16
  - RUBY VERSION: 2.6.3 (2019-04-16 patchlevel 62) [universal.x86_64-darwin20]
  - INSTALLATION DIRECTORY: /Library/Ruby/Gems/2.6.0
  - USER INSTALLATION DIRECTORY: /Users/sandyboy/.gem/ruby/2.6.0
  - RUBY EXECUTABLE: /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/bin/ruby
  - GIT EXECUTABLE: /usr/local/bin/git
  - EXECUTABLE DIRECTORY: /usr/bin
  - SPEC CACHE DIRECTORY: /Users/sandyboy/.gem/specs
  - SYSTEM CONFIGURATION DIRECTORY: /Library/Ruby/Site
  - RUBYGEMS PLATFORMS:
     - ruby
     - universal-darwin-20
  - GEM PATHS:
     - /Library/Ruby/Gems/2.6.0
     - /Users/sandyboy/.gem/ruby/2.6.0
     - /System/Library/Frameworks/Ruby.framework/Versions/2.6/usr/lib/ruby/gems/2.6.0
  - GEM CONFIGURATION:
     - :update_sources => true
     - :verbose => true
     - :backtrace => false
     - :bulk_threshold => 1000
     - :gemdir => ["~/.gem/ruby"]
     - "install" => "-n /usr/local/bin"
  - REMOTE SOURCES:
     - https://rubygems.org/
  - SHELL PATH:
     - /usr/local/bin
     - /usr/bin
     - /bin
     - /usr/sbin
     - /sbin
     - /Users/sandyboy/.rvm/bin
   ```
  - `RUBY VERSION` : This is the version number of Ruby associated with the gem you just ran. Each version of Ruby has its own `gem` command.
  - `RUBY EXECUTABLE` : This is the location of the ruby command that you should use with the Gems managed by this gem command. This information is often useful when `RUBY VERSION` reveals a `gem/ruby` mismatch. (WHha?)
  - `INSTALLATION DIRECTORY` : This directory is where `gem` installs Gems by default.
  - `USER INSTALLATION DIRECTORY`
  - `EXECUTABLE INSTALLATION DIRECTORY`
  - `REMOTE SOURCES`
  - `SHELL PATH`

#### Which file was required?
