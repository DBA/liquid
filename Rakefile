#!/usr/bin/env ruby
begin
  require 'jeweler'
  Jeweler::Tasks.new do |gemspec|
    gemspec.name = "liquid"
    gemspec.summary = "A secure non evaling end user template engine with aesthetic markup."
    gemspec.description = "A secure non evaling end user template engine with aesthetic markup. Liquid currently supports Ruby versions 1.8.7, 1.9.1 and 1.9.2. This version of the gem is currently being tested with Ruby on Rails 3 beta 4."
    gemspec.email = "tobi@leetsoft.com"
    gemspec.homepage = "http://www.liquidmarkup.org"
    gemspec.authors = ["Tobias Luetke"]

    # dependencies defined in Gemfile
  end
rescue LoadError
  puts "Jeweler not available. Install it with: gem install jeweler"
end

begin
  require 'rake/testtask'
  Rake::TestTask.new(:test) do |t|
    t.libs << "lib" << 'test'
    t.pattern = 'test/*_test.rb'
    t.verbose = false
  end
rescue LoadError
  puts "rake is not available. install it with: gem install rake"
end

namespace :profile do
  task :default => [:run]

  desc "Run the liquid profile/perforamce coverage"
  task :run do
    ruby "performance/shopify.rb"
  end

  desc "Run KCacheGrind" 
  task :grind => :run  do
    system "kcachegrind /tmp/liquid.rubyprof_calltreeprinter.txt"
  end
end