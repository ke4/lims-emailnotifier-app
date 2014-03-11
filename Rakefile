#require 'rspec/core/rake_task'

task :run => ["dev:run"]
task :default => [:test]

#RSpec::Core::RakeTask.new(:spec) do |task|
#  task.rspec_opts = '--color'
#end

task :test do
  sh "bundle exec rspec"
end

namespace :dev do
  task :setup_env do
    ENV["LIMS_EMAILNOTIFIER_ENV"] = "development"
  end

  task :run => :setup_env do
    sh "bundle exec ruby script/start_emailnotifier.rb"
  end
end
