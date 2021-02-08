require 'html-proofer'

task :test do
  Rake::Task["reset"].invoke
  Rake::Task["build"].invoke

  opts = {
    check_external_hash: true,
    allow_hash_href: true,
    check_html: true,
    disable_external: true,
    empty_alt_ignore: true,
    assume_extension: true,
    only_4xx: true,
    verbose: true
  }
  $stdout.reopen("log.txt", "w")
  HTMLProofer.check_directory('./_site', opts).run
end

task :reset do
  sh "rm -rf _site .jekyll*"
end

task :build do
  sh "bundle exec jekyll build -d _site/sanger-repotted"
end