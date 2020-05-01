require "bundler/gem_tasks"
require "rake/testtask"
require 'find'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'List inventory of project files'
task :files do
  Find.find(File.absolute_path('.')) do |path|
    Find.prune if File.basename(path).start_with?('/.')
    puts path if File.file?(path)
  end
end

desc 'List inventory of project files'
task :inventory do
  Find.find('.') do |name|
    next if name.include?('/.') # excludes hidden . files and directories
    puts name if File.file?(name)
  end
end
