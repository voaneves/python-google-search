<a id="top"></a>

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/logo/logo-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/logo/logo-light.svg" />
  <img alt="Python Google Search logo: the monogram GS" src="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/logo/logo-light.svg" width="112" height="112" />
</picture>

<h1>Python Google Search</h1>

<p>
  <strong>Command-line script that runs a Google search and collects the first 10 result URLs.</strong><br />
  <sub>Uses the google package (googlesearch module)</sub>
</p>

<p>
  <a href="https://voaneves.github.io/python-google-search/"><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/buttons/landing-dark.svg" /><img alt="View landing page" src="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/buttons/landing-light.svg" height="40" /></picture></a>
  <a href="https://github.com/voaneves/python-google-search/blob/main/google_search.py"><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/buttons/script-dark.svg" /><img alt="View the script" src="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/buttons/script-light.svg" height="40" /></picture></a>
</p>

<p><sub>Need something like this? <a href="https://voaneves.com/en/#contact"><strong>Let's talk →</strong></a></sub></p>

<p>
  <a href="https://github.com/voaneves/python-google-search/blob/main/LICENSE"><img src="https://img.shields.io/github/license/voaneves/python-google-search?style=flat-square&color=0A0A0A" alt="MIT License" /></a>
  <img src="https://img.shields.io/badge/Python-3-b80000?style=flat-square" alt="Python 3" />
  <a href="https://github.com/voaneves/python-google-search/issues"><img src="https://img.shields.io/github/issues/voaneves/python-google-search?style=flat-square&color=0A0A0A" alt="Open issues" /></a>
</p>

<p>
  <a href="#what-it-does">What it does</a> ·
  <a href="#installation">Installation</a> ·
  <a href="#usage">Usage</a> ·
  <a href="#limitations">Limitations</a> ·
  <a href="#responsible-use">Responsible use</a> ·
  <a href="#contact">Contact</a>
</p>

</div>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/brand/rule-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/brand/rule-light.svg" />
  <img alt="" src="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/brand/rule-light.svg" width="100%" />
</picture>

## What it does

Run it with a search phrase and it collects the URLs of the first ten Google results into a Python list.

`google_search.py` takes a search string as a command-line argument, turns spaces into `+`, queries Google (`tld="com"`, `num=10`, `stop=10`, `pause=2` seconds between requests) and stores the result URLs in a list called `results`.

## Installation

Requires Python 3.

```bash
git clone https://github.com/voaneves/python-google-search.git
cd python-google-search
pip install google
```

Note: the repository does not ship a `requirements.txt` yet. The only dependency is the `google` package, which provides the `googlesearch` module imported by the script.

## Usage

Pass the query as a single quoted argument:

```bash
python google_search.py "string to be searched"
```

## How it works

1. Reads the arguments from `sys.argv[1:]` and joins them into one string.
2. Replaces spaces with `+` to build the query.
3. Calls `googlesearch.search(query, tld="com", num=10, stop=10, pause=2)` and appends each URL to `results`.

## Limitations

- The script builds `results` but does **not** print or save it yet; add your own `print`/export, or adapt the loop. Saving to a formatted file and better result metadata (titles, descriptions) are listed as TODO in the source.
- Arguments are joined without spaces, so always wrap the query in quotes.
- Only URLs are returned, no titles or snippets.
- Google may rate-limit or block automated queries (HTTP 429/captcha). Keep the `pause` delay.

## Responsible use

Automated querying may violate [Google's Terms of Service](https://policies.google.com/terms). Use it for learning, small personal experiments and low volume only, respect rate limits, and consider the official [Custom Search JSON API](https://developers.google.com/custom-search/v1/overview) for anything serious. You are responsible for how you use this code.

## Security note

The `googlesearch` library stores a session cookie in a local `.google-cookie` file. It is a credential: it is listed in `.gitignore` and must never be committed or shared. If a cookie was ever published, treat it as compromised and sign out of / invalidate that Google session.

## Em português

Script Python que faz uma busca no Google pela linha de comando e guarda as 10 primeiras URLs de resultado na lista `results`, usando o pacote `google` (módulo `googlesearch`).

- Instalação: `pip install google`
- Uso: `python google_search.py "texto da busca"` (use aspas)
- Limitações: o script ainda não imprime nem salva os resultados; só retorna URLs; o Google pode bloquear consultas automatizadas.
- Segurança: o arquivo `.google-cookie` guarda um cookie de sessão; nunca o versione nem o compartilhe.
- Uso responsável: automatizar buscas pode violar os Termos de Serviço do Google. Use com moderação ou prefira a API oficial (Custom Search JSON API).

## Contact

<p>
  <a href="https://voaneves.com/en/#contact"><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/buttons/hire-dark.svg" /><img alt="Let's talk" src="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/buttons/hire-light.svg" height="40" /></picture></a>
  <a href="https://voaneves.com/en/"><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/buttons/site-dark.svg" /><img alt="voaneves.com" src="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/buttons/site-light.svg" height="40" /></picture></a>
</p>

<a href="https://linkedin.com/in/voaneves">LinkedIn</a> · <a href="mailto:victorneves478@gmail.com">E-mail</a>

<p align="center">
  <img alt="VOANEVES mark" src="https://raw.githubusercontent.com/voaneves/python-google-search/main/assets/brand/mark-duo.svg" width="32" height="32" />
</p>

<p align="center"><sub>Released under the <a href="https://github.com/voaneves/python-google-search/blob/main/LICENSE">MIT License</a>.</sub></p>

<p align="center"><sub><a href="#top">↑ Back to top</a></sub></p>
