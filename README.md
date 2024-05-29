# rails_templates
## For Mac

1. Rails アプリの作成
```
rails new XXX -c tailwind -d postgresql
```
2. Gem 関係インストール
```   
# 追加分
gem 'bullet'
gem 'dotenv-rails'
gem 'rails-i18n'
gem 'rubocop'
gem 'rubocop-performance'
gem 'rubocop-rails'
gem 'rubocop-rspec'

group :development, :test do
  # See https://guides.rubyonrails.org/debugging_rails_applications.html#debugging-with-the-debug-gem
  gem 'debug', platforms: %i[mri windows]
  gem 'rspec-rails'
end
```
3. ``bundle install``
4. Rubocop関係
```
bundle exec rubocop --auto-gen-config
```
```
AllCops:
  NewCops: enable
  Exclude:
    - 'bin/**/*'
    - 'db/migrate/**/*'
    - 'db/schema.rb'
    - 'vendor/**/*'

Style/Documentation:
  Enabled: false

require:
  - rubocop-capybara
  - rubocop-rails
  - rubocop-rspec
  - rubocop-performance
  - rubocop-rspec_rails
```
```
rubocop -A
```
5. Rspec関係
```
bin/rails g rspec:install
```
```
--require spec_helper
--format documentation
```
```
bundle exec rspec 
bundle binstubs rspec-core
```
config/app.rb
```
# 追加分
    config.generators do |g|
      g.test_framework :rspec,
                       fixtures: false,
                       view_specs: false,
                       helper_specs: false,
                       routing_specs: false
    end
```

6. DBの作成
```
brew search postgresql
```
```
brew services start postgresql@最新版
 or
brew services stop postgresql@最新版
```
```
rails db:create
```



---



## For WSL

1. Rails アプリの作成
```
rails new XXX -c tailwind -d postgresql
```
2. Gem 関係インストール
```   
# 追加分
gem 'bullet'
gem 'dotenv-rails'
gem 'rails-i18n'
gem 'rubocop'
gem 'rubocop-performance'
gem 'rubocop-rails'
gem 'rubocop-rspec'

group :development, :test do
  # See https://guides.rubyonrails.org/debugging_rails_applications.html#debugging-with-the-debug-gem
  gem 'debug', platforms: %i[mri windows]
  gem 'rspec-rails'
end
```
3. ``bundle install``
4. Rubocop関係
```
bundle exec rubocop --auto-gen-config
```
```
AllCops:
  NewCops: enable
  Exclude:
    - 'bin/**/*'
    - 'db/migrate/**/*'
    - 'db/schema.rb'
    - 'vendor/**/*'

Style/Documentation:
  Enabled: false

require:
  - rubocop-capybara
  - rubocop-rails
  - rubocop-rspec
  - rubocop-performance
  - rubocop-rspec_rails
```
```
rubocop -A
```
5. Rspec関係
```
bin/rails g rspec:install
```
```
--require spec_helper
--format documentation
```
```
bundle exec rspec 
bundle binstubs rspec-core
```
config/app.rb
```
# 追加分
    config.generators do |g|
      g.test_framework :rspec,
                       fixtures: false,
                       view_specs: false,
                       helper_specs: false,
                       routing_specs: false
    end
```

6. DBの作成
```
要確認して記載
```
```
sudo service postgresql start
 or
sudo service postgresql stop
```
```
rails db:create
```
