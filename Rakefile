require 'middleman-gh-pages'
require 'rake/clean'

CLOBBER.include('build')


task :build_slate do
  puts "building slate"
  sh "bundle exec middleman build"
end

task :copy_swagger do
  puts "copying swagger UI"
  sh "cp build public -r"
  sh "cp -r api public/api"
end

task :run_server do
  sh "bundle install"
  sh "ruby -run -ehttpd ./public -p4567"
end
task :run => [:build_slate, :copy_swagger, :run_server]

task :static => [:build_slate, :copy_swagger]