require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = 'email_veracity'
    gem.summary = 'A simple library for checking the real-world validity of email addresses.'
    gem.description = 'Email Veracity abstracts an email address into a series of objects which makes it easy to see if an address is invalid, and if so, why.'
    gem.email = 'heycarsten@gmail.com'
    gem.homepage = 'http://github.com/heycarsten/email-veracity'
    gem.authors = 'Carsten Nielsen'

    gem.add_dependency 'activemodel', '>= 3.0.0'

    gem.add_development_dependency 'test-unit', '>= 2.1.1'
    gem.add_development_dependency 'bundler', '>= 1.0.0.rc.3'
    gem.add_development_dependency 'mocha', '>= 0.9.8'
    gem.add_development_dependency 'shoulda', '>=2.11.3'
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/test_*.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => :test

require 'rdoc/task'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "email-veracity #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
