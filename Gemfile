source 'https://rubygems.org'

gem "jekyll"

# The gem packages come from the system, e.g. Debian packages.  The
# gems from git should be referenced using a commit ID ref to provide
# a strong verified link to the source code.  The production site
# verifies a signed git tag, which then will include the SHA1 commit
# ID, which git will verify.
group :jekyll_plugins do
    gem "jekyll-redirect-from"
    gem "jekyll-paginate-v2"
    gem "jekyll-polyglot", :git => 'https://gitlab.com/fdroid/jekyll-polyglot.git',
        :ref => 'b4520fd8c638d43b6b96abd8b4462b1a398bb0e2'  # 1.8.0
    gem 'jekyll-fdroid', :git => 'https://gitlab.com/g0tmi1k/jekyll-fdroid.git',
        :ref => '6d64cf87fae7bc4e76dd5479048877d58a3af5c5'
    gem 'git'
end
