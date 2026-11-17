# python-google-search

> Tiny Python script that runs a Google Search from the command line and collects the first 10 result URLs, using the [`google`](https://pypi.org/project/google/) package (`googlesearch` module).

**Keywords:** python google search, google search automation, command line google search, scrape google results, googlesearch, python script.

## What it does

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

## License

MIT, see [LICENSE](LICENSE).