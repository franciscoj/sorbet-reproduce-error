# Error example:

sorbet version: 

```
sorbet (0.5.5994)
  sorbet-static (= 0.5.5994)
sorbet-runtime (0.5.5994)
sorbet-static (0.5.5994-universal-darwin-14)
```

Example code:

```ruby
class Test
  def m(_, _)
    puts "Hi!"
  end
end
```

When a method is declared with 2 "ignored" parameters with `_` sorbet
fails when running `bundle exec srb rbi init` with a message like:

```
Naming all Modules
Naming Bundler::ThorGot LoadError when trying to get nested name Bundler::Thor::RakeCompat
Naming Gem/home/user/.asdf/installs/ruby/2.6.6/lib/ruby/gems/2.6.0/gems/sorbet-0.5.5994/lib/real_stdlib.rb:77: warning: constant Gem::RubyGemsVersion is deprecated
/home/user/.asdf/installs/ruby/2.6.6/lib/ruby/gems/2.6.0/gems/sorbet-0.5.5994/lib/real_stdlib.rb:77: warning: constant Gem::ConfigMap is deprecated
Naming Struct/home/user/.asdf/installs/ruby/2.6.6/lib/ruby/gems/2.6.0/gems/sorbet-0.5.5994/lib/real_stdlib.rb:77: warning: constant Struct::Tms is deprecated
Generating /tmp/d20201023-379925-1s5ppha/reflection.rbi with 900 modules and 36 aliases
Printing your code's symbol table into /tmp/d20201023-379925-1s5ppha/from-source.json
Printing /tmp/d20201023-379925-1s5ppha/reflection.rbi's symbol table into /tmp/d20201023-379925-1s5ppha/reflection.json
Traceback (most recent call last):
	6: from /home/user/.asdf/installs/ruby/2.6.6/lib/ruby/gems/2.6.0/gems/sorbet-0.5.5994/bin/srb-rbi:237:in `<main>'
	5: from /home/user/.asdf/installs/ruby/2.6.6/lib/ruby/gems/2.6.0/gems/sorbet-0.5.5994/bin/srb-rbi:196:in `main'
	4: from /home/user/.asdf/installs/ruby/2.6.6/lib/ruby/gems/2.6.0/gems/sorbet-0.5.5994/bin/srb-rbi:121:in `init'
	3: from /home/user/.asdf/installs/ruby/2.6.6/lib/ruby/gems/2.6.0/gems/sorbet-0.5.5994/bin/srb-rbi:232:in `block in make_step'
	2: from /home/user/.asdf/installs/ruby/2.6.6/lib/ruby/gems/2.6.0/gems/sorbet-0.5.5994/lib/hidden-definition-finder.rb:38:in `main'
	1: from /home/user/.asdf/installs/ruby/2.6.6/lib/ruby/gems/2.6.0/gems/sorbet-0.5.5994/lib/hidden-definition-finder.rb:47:in `main'
/home/user/.asdf/installs/ruby/2.6.6/lib/ruby/gems/2.6.0/gems/sorbet-0.5.5994/lib/hidden-definition-finder.rb:151:in `write_constants': /tmp/d20201023-379925-1s5ppha/reflection.rbi had unexpected errors. Check this file for a clue: /tmp/d20201023-379925-1s5ppha/reflection.json.err (RuntimeError)
```

To easily reproduce, try running  `bundle exec srb rbi init` in this
example project

