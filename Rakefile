require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "resque-multiple-failure-backend"
    gem.summary = %Q{Adds a failed queue for each queue}
    gem.description = %Q{Individual failed queue for each queue you have}
    gem.email = "Ads.noob@gmail.com"
    gem.homepage = "http://github.com/omgitsads/resque-multiple-failure-backend"
    gem.authors = ["Adam Holt"]
    gem.add_development_dependency "thoughtbot-shoulda", ">= 0"
    gem.files = FileList["[A-Z]*", "{bin,generators,lib,test}/**/*", 'lib/jeweler/templates/.gitignore']
    gem.add_dependency "resque", ">= 0"
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

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "resque-multiple-failure-backend #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
