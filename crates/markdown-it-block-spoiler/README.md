<div align="center">
  <img src="https://img.shields.io/crates/l/markdown-it-block-spoiler?style=for-the-badge" alt="License" />
  <img src="https://img.shields.io/crates/v/markdown-it-block-spoiler?style=for-the-badge" alt="Latest version" />
  <img src="https://img.shields.io/crates/dv/markdown-it-block-spoiler?style=for-the-badge" alt="Downloads for latest version" />
</div>
# markdown-it-spoiler.rs

A [`markdown-it`](https://crates.io/crates/markdown-it) plugin to process block spoliers.

To load the plugin:

```rust
let mut parser = markdown_it::MarkdownIt::new();
markdown_it::plugins::cmark::add(&mut parser);

markdown_it_block_spoiler::add(&mut parser);

let html = parser.parse("::: spoiler _click to see more_\nhow spicy!\n:::\n").xrender();
assert_eq!(html, String::from("<details><summary>_click to see more_</summary>how spicy!\n</details>\n"));
```

If you are using this plugin in the browser, you can use the "browser" feature to have this library use built-in browser libraries to keep the bundle size down.

``` toml
markdown-it-spoiler = { version = "1", default-features = false, features = ["browser"] }
```