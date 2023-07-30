<div align="center">
<h1>Paper <sup><sup><sub>6.19</sub></sup></sup></h1>

Demo → [hugo-paper.vercel.app](https://hugo-paper.vercel.app/)

<hr />

A simple, clean, customizable Hugo theme.

⚡️ Fast | 👒 Customizable (`linen` ░ `wheat` ░ `gray` ░ `light`) | 🫙 Smooth

</div>

---

## Options

Available options to `config.toml` or `hugo.toml`:

```toml
disqusShortname = 'YOUR_DISQUS_SHORTNAME'   # use disqus comments

[params]
  # color style
  color = 'linen'                           # linen, wheat, gray, light

  # header social icons
  twitter = 'YOUR_TWITTER_ID'               # twitter.com/YOUR_TWITTER_ID
  github = 'YOUR_GITHUB_ID'                 # github.com/YOUR_GITHUB_ID
  instagram = 'YOUR_INSTAGRAM_ID'           # instagram.com/YOUR_INSTAGRAM_ID
  linkedin = 'YOUR_LINKEDIN_ID'             # linkedin.com/in/YOUR_LINKEDIN_ID
  mastodon = 'YOUR_MASTODON_LINK'           # e.g. 'https://mastodon.instance/@xxx'
  rss = true                                # show rss icon

  # home page profile
  avatar = 'GRAVATAR_EMAIL'                 # gravatar email or image url
  name = 'YOUR_NAME'
  bio = 'YOUR_BIO'


  # misc
  disableHLJS = true                        # disable highlight.js
  monoDarkIcon = true                       # show monochrome dark mode icon
  gravatarCdn = 'GRAVATAR_CDN_LINK'         # e.g. 'https://cdn.v2ex.com/gravatar/'
  graphCommentId = "YOUR_GRAPH_COMMENT_ID"  # use graph comment (disqus alternative)
  math = true                               # enable KaTex math typesetting globally
```

Available options to front matter:

```toml
comments = false                            # disable comments for a specific page
math = true                                 # enable KaTex math typesetting for a specific page
```

## Install

Inside the folder of your Hugo project, run:

```bash
git submodule add https://github.com/nanxiaobei/hugo-paper themes/paper
```

Open `config.toml` or `hugo.toml`, change `theme` to `"paper"`:

```toml
theme = "paper"
```

For more information, please read the [official guide](https://gohugo.io/getting-started/quick-start/#step-3-add-a-theme) of Hugo.

## License

[MIT License](https://github.com/nanxiaobei/hugo-paper/blob/main/LICENSE) (c) [nanxiaobei](https://lee.so/)

