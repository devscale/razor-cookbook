#!/usr/bin/env rake
require 'rake/testtask'
require 'foodcritic'

FoodCritic::Rake::LintTask.new do |t|
  t.options = { :fail_tags => ['any'] }
end

begin
  require 'jamie/rake_tasks'
  Jamie::RakeTasks.new
rescue LoadError
  puts ">>>>> Jamie gem not loaded, omitting tasks" unless ENV['CI']
end

desc "Run all test suites"
task :test_all => [:default, :jamie]

task :default => [:foodcritic]
