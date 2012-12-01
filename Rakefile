# encoding: utf-8

require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options
  gem.name = "bio-tm_hmm"
  gem.homepage = "http://github.com/wwood/bioruby-tm_hmm"
  gem.license = "MIT"
  gem.summary = %Q{A bioruby plugin for interaction with the transmembrane predictor TMHMM}
  gem.description = %Q{A bioruby plugin for interaction with the transmembrane predictor TMHMM}
  gem.email = "donttrustben@gmail.com"
  gem.authors = ["Ben J. Woodcroft"]
  # dependencies defined in Gemfile
end
Jeweler::RubygemsDotOrgTasks.new

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end
Rake::TestTask.new(:test_without_tmhmm) do |test|
  test.libs << 'lib' << 'test'
  test.test_files = FileList['test/test*.rb'].reject{|f| f=='test/test_tm_hmm_wrapper.rb'}
  test.verbose = true
end

task :default => :test

require 'rdoc/task'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "bio-tm_hmm #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
