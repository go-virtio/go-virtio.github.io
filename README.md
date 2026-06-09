# go-virtio.github.io

Sources for **go-virtio.github.io** — the go-virtio landing page.
Built by [Hugo](https://gohugo.io) — same toolchain and same template
shape as [cloud-boot.github.io](https://github.com/cloud-boot/cloud-boot.github.io)
and [openweft.github.io](https://github.com/openweft/openweft.github.io).
Slate-blue palette so it reads as a sibling project page.

## Layout

```text
.
├── hugo.toml                       Site config + hero params
├── content/
│   └── _index.md                   Homepage marker (empty)
├── data/
│   └── mesh.toml                   Stack visualisation: drivers / common / host
├── layouts/
│   ├── _default/baseof.html        Outer HTML shell
│   ├── index.html                  Homepage body (go-virtio specific)
│   └── partials/
│       ├── nav.html                Topnav with brand + menu
│       ├── footer.html             Footer
│       └── mesh.html               Animated SVG (reads data/mesh.toml)
├── static/
│   └── css/main.css                Slate-blue palette + mesh styling
└── public/                         Hugo build output (gitignored — built by CI)
```

## Build locally

```sh
hugo server -D                            # live reload at http://localhost:1313/
hugo --gc --minify                        # production build → ./public/
```

## Deploy

`.github/workflows/hugo.yml` builds + deploys on every push to `main`.
Configure GitHub Pages on the repo with **Source = "GitHub Actions"**
(not "Deploy from a branch").

## Sibling pages

- [cloud-boot](https://cloud-boot.github.io) — the UEFI bootloader and
  UKI toolchain that go-virtio's first consumer ships in.
- [openweft](https://openweft.github.io) — the cloud platform on top.
