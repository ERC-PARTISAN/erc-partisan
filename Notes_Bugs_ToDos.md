# Partisan Website

## Notes

**URL:** https://erc-partisan.github.io



## Step-By-Step Guide

1. Requirements: Homebrew, Ruby, and Jekyll, Bundler

   - Install Homebrew

   - https://jekyllrb.com/docs/installation/macos/
   - Do not use 'chruby' since it does not allow to install the newest Ruby version due to a bug
   -  Instead, use rbenv to install ruby: https://www.engineyard.com/blog/how-to-install-ruby-on-a-mac-with-chruby-rbenv-or-rvm/ 
     - scroll down until rbenv instructions
   - install Jekyll
   - install bundler

2. Remove the 'ruby-version' file in the github repo

   - see issue discussion https://github.com/amitmerchant1990/reverie/issues/57

3. Navigate with the terminal to the working directory

   - use the command 'ls' to see where you currently are
   - use the command 'cd' to change the directory (navigate through the folders with 'cd')

4. Create a new 'Gemfile'

   - A gemfile is just a simple text document without a file ending - the document name has to be just 'Gemfile'

   - The Gemfile need to include

     ```Gemfile
     source 'https://rubygems.org'
     gem 'jekyll-sitemap'
     gem 'jekyll-feed'
     gem 'jekyll-seo-tag'
     gem 'jekyll-paginate'
     ```

   - the gems are specified the '_config.yml' file

5. Install the gem dependencies

   ```Terminal
   bundle add jekyll-seo-tag jekyll-paginate jekyll-sitemap jekyll-feed
   ```

6. Install a further needed dependency

   ```Terminal
   gem install github-pages webrick
   ```

7. Test the Website locally

   ```Terminal
   jekyll serve
   ```

   - The terminal has to be in the correct working directory!
   - copy the server address and test the website in a browser

8. Change individual pages

   - open the md files
   - in the header sections meta data can be included
   - then just use markdown



## NEW Protocol

1. Navigate with the terminal to the working directory

   - use the command 'ls' to see where you currently are
   - use the command 'cd' to change the directory (navigate through the folders with 'cd')

2. Run in terminal

   ```
   bundle install
   ```

3. Start the Jekyll local development server

   ```
   bundle exec jekyll serve
   ```

   



