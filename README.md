# Minimal Ruby App Template

This is a basic boilerplate template for a minimal Ruby application.  It includes:

  * A `Gemfile` with rspec, rubocop, and rake.
  * A `lib` directory for your code files.
  * A `spec` directory for your RSpec tests.
  * Configuration for rspec.
  * Configuration for rubocop.
  * A `script/test` for running linting and tests.
  * A `bundle exec rake console` task to open an IRB console to play around with the code.
  * A `README.md` with some getting started instructions.
  * A `.gitignore` for Ruby (taken from https://github.com/github/gitignore/blob/master/Ruby.gitignore).



## Getting started

This project uses the [Ruby] programming language.

To work with this project, the first step is to ensure you have Ruby installed.  The expected Ruby version is specified in the `.ruby-version` file and also in `Gemfile`.

If you are using a Mac, some popular ways to install Ruby include [asdf] (with the [asdf-ruby](https://github.com/asdf-vm/asdf-ruby) plugin), or [rbenv]. You can also use [homebrew] but this makes it difficult to manage multiple Ruby versions at the same time.

Dependencies are managed using [Bundler].  Install dependencies with:

```bash
bundle config set path 'vendor/bundle'
bundle install
```

The first line in the above is optional but recommended, as it ensures that your gems (Ruby's term for external dependencies) are installed specific to this project in a subdirectory, rather than globally for this whole Ruby version (which could affect other projects).

When running any ruby commands (e.g. running tests) we'll prefix them with `bundle exec` to ensure that Bundler has made the specific gems, that this project requires, available.

### Running tests

This project uses [RSpec] for testing.

Run specs with:

```bash
bundle exec rspec
```

You can run a specific spec by specifying the filename:

```bash
bundle exec rspec spec/some_spec.rb
```

You can even run a specific example by specifying the filename and line number:

```bash
bundle exec rspec spec/some_spec.rb:11
```

RSpec is configured via `.rspec` and `spec/spec_helper.rb`.

### Linting

This project uses [Rubocop] for linting and code formatting.

Rubocop is configured via the `.rubocop.yml` file.

The conventions used in this project are arbitrary and based on my personal preferences.  The main purpose of using Rubocop here is to enforce consistency, which helps avoid bikeshedding over coding style and hopefully makes the code a little easier to read.

### Running tests and linting

To run tests and linting, you can use:

```bash
script/test
```

### Interactive console

To open an IRB console, which is useful for debugging and trying stuff out, you can use:

```bash
bundle exec rake console
```

Once you've finished, you can type `exit` (and hit `<return>`) within the IRB console to exit.

### Project structure

The structure of this project is as follows:

```
├── .rspec         # configuration for RSpec (for testing)
├── .rubocop.yml   # configuration for Rubocop (code linting)
├── .ruby-version  # specifies the version of Ruby that this project expects
├── Gemfile        # specifies project dependencies
├── Gemfile.lock   # managed by Bundler to track specific version of installed dependencies
├── Rakefile       # specifies available Rake tasks availalable from the command line (use `bundle exec rake -T` to list them)
├── README.md      # you're reading it!
├── lib/           # source code lives in here
├── script/        # utility scripts
├── spec/          # RSpec tests (for the code in `lib`)
└── vendor/        # dependencies (gems) installed by Bundler are stored here; this is not tracked by version control
```

Where possible, the file structure under `lib` correlates to the code namespaces.


[Ruby]:https://www.ruby-lang.org/en/
[asdf]:https://github.com/asdf-vm/asdf
[rbenv]:https://github.com/rbenv/rbenv
[homebrew]:https://brew.sh/
[Bundler]:https://bundler.io/
[RSpec]:https://rspec.info/
[Rubocop]:https://github.com/rubocop/rubocop
