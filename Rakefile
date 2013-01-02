require File.expand_path("lib/i18n_export/version", File.dirname(__FILE__))
require 'rake/testtask'

namespace :build do
  desc "builds the gem"
  task :gem do
    `gem build i18n-export.gemspec`
  end

  desc "builds and installs the gem into your local rubygems"
  task :install => [:gem] do
    `gem install i18n-export-#{I18nExport::Version::STRING}.gem`

    Rake::Task["build:clean"].invoke
  end

  task :clean do
    system "rm i18n-export-#{I18nExport::Version::STRING}.gem"
  end
end

desc 'Test the i18n-export gem.'
Rake::TestTask.new(:test) do |t|
  t.libs << 'lib'
  t.pattern = 'test/test_*.rb'
  t.verbose = true
end

desc 'Default: run unit tests.'
task :default => :test


