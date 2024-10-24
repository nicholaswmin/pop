# nix   

> [WIP]
>
> [hyper minimal][concise] blogging framwork written in Ruby,   
> inspired by Bradley Taunt's [wruby][wruby] & the [1kb club][club]
>
> `nix` means *nothing* in rejective form.


## install

It's a single-file, `nix.rb`.     
Download [nix.rb][file], drop it in a folder, and:

```bash
# or nix -i
ruby nix.rb --init
```

creates a sample blog.
Add posts as [gfm markdown][gfm] in `/posts` and:

```bash
ruby nix.rb
```

outputs all `HTML` in `/build`.

In case you don't have [ruby][ruby]:

```bash
brew install ruby
```

Download `nix.rb`, drop it in a folder, then:

> generate sample blog:

```bash
ruby nix.rb --init
```

> build:

ruby nix.rb --init
```

builds all `HTML` in `build/`.

## usage 

It's like [Jekyll][jekyll]. You write [Github-flavored Markdown][gfm].

> inc. syntax highlighting for 150 languages via [`pygments`][pygments]

- Add posts in `posts/`
- Add pages in `pages/`

They *must* have an:

- `# <post-title>` on the 1st line
- `empty line` on the 2nd
- `<date>` on the 3rd, ie. `2024-10-18`

Example post (or page):

```markdown
# Lorem Ipsum

2024-12-20

A sentence should contain no unnecessary words, a paragraph no unnecessary 
sentences, for the same reason that a drawing should have no unnecessary lines 
and a machine no unnecessary parts. This requires not that the writer make all 
his sentences short, or that he avoid all detail and treat his subjects only 
in outline, but that every word tell

The Elements of Style by William Strunk Jr (1918) ...
```

additionally:

- images go in `public/`.
- css are in `public/style.css`
- config site via `_config.rb`

## build

just run:

```bash
ruby nix.rb
```

outputs all in `build/`.

### Rebuild on file change

> Tired of pressing `save` on every change?

Grab [`fswatch`][fswatch]:

```bash
brew install fswatch
```

then run:

```js
fswatch -o -r -d ./ -e build | xargs -n1 -I{} make build & ruby -run -e httpd -- build
```

Written for testability, in [*idiomatic Ruby*][id-ruby].

## test

```bash
@todo
```

## conventions

- follows [Semantic HTML][semantic-html] & the [ARIA specs][aria]
- designed for testability, written in [*idiomatic Ruby*][id-ruby].
- [suckless philosophy][suckless]

## License

[The MIT License](https://spdx.org/licenses/MIT)

[club]: https://1kb.club/
[ruby]: https://ruby-doc.org/3.3.4/
[wruby]: https://git.btxx.org/wruby/about/
[jekyll]: https://jekyllrb.com/
[concise]: https://en.wikipedia.org/wiki/Concision
[fswatch]: https://github.com/emcrisostomo/fswatch
[gfm]: https://github.github.com/gfm/
[id-ruby]: https://franzejr.github.io/best-ruby/idiomatic_ruby/conditional_assignment.html
[pygments]: https://pygments.org/

[suckless]: https://suckless.org/philosophy/
[semantic-html]: https://html.spec.whatwg.org/multipage/#toc-dom
[aria]: https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA
