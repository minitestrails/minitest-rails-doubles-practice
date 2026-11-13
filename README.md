# Minitest Rails doubles practice

Practice app for [Chapter 17 - Test Doubles in Minitest](https://minitestrails.com/guide/stubs-and-doubles-in-minitest/) in the Minitest Rails guide.

Auth0 login is already wired the same way as the [Auth0 blog companion](https://github.com/minitestrails/auth0-minitest-rails). The test folder is empty on purpose. You add the stub and mock examples from the chapter here, not in your Cookbook app.

## Prerequisites

- Ruby 4.0.2 (see `.ruby-version`)
- Rails 8.1.3
- An [Auth0](https://auth0.com/) account only if you want to click Login in the browser. Tests do not need real Auth0 credentials.

## Local setup

```bash
cd minitest-rails-doubles-practice
bin/setup --skip-server
```

`bin/setup` copies `config/auth0.yml.example` to `config/auth0.yml` if it does not exist.

To try login in the browser, edit `config/auth0.yml` with your Auth0 credentials, then:

```bash
bin/rails server
```

Visit [http://localhost:3000](http://localhost:3000), click **Login**, and complete Auth0 sign-in. You are redirected to `/dashboard`.

Auth0 application URIs:

- **Allowed Callback URLs**: `http://localhost:3000/auth/auth0/callback`
- **Allowed Logout URLs**: `http://localhost:3000`

## What is already here

- OmniAuth Auth0 in `config/initializers/auth0.rb`
- `Auth0Controller` callback, failure, and logout
- `User.find_or_create_from_auth0`
- OmniAuth test mode in `config/environments/test.rb` (no real Auth0 in the suite)
- `minitest-mock` in the `:test` group and `require "minitest/mock"` in `test/test_helper.rb`
- Alice fixture in `test/fixtures/users.yml` (`auth0|test-user-1`)

## Tests

There are no examples yet. Follow the chapter and add files under `test/`.

```bash
bin/rails test
bin/rails test:all
```

You should see 0 runs until you add tests. Keep real Auth0 domain, client ID, and client secret out of the test path.
