task :default => [:package]

task :test do
  system("cd test/globtail && make")
  system("ruby test/filewatch/tail.rb")
end

task :package => [:test, :package_real]  do
end

task :package_real do
  system("gem build filewatch.gemspec")
end

task :publish do
  latest_gem = %x{ls -t filewatch*.gem}.split("\n").first
  system("gem push #{latest_gem}")
end
