### 🧠 `README.md` para o repositório `BUGHUNTBR`

```markdown
# 🕷️ BUGHUNTBR

Ferramenta de automação de reconhecimento e testes iniciais para programas de Bug Bounty. Desenvolvida em Python para facilitar a coleta de informações, análise de parâmetros, e detecção rápida de vulnerabilidades como XSS, IDOR, tokens expostos e muito mais.

## ✨ Destaques

- 🔍 Reconhecimento automatizado com subfinder, httpx, gau, waybackurls, gospider
- ⚔️ Testes de XSS com `qsreplace` + `dalfox`
- 🔑 Busca por tokens expostos (strings de 20+ caracteres)
- 🧩 Busca por IDOR (URLs com padrões como `id=`, `user_id=`)
- 📊 Scanner com Nuclei e suporte a templates
- ⏱️ Suporte a `--quick` (testes rápidos com 5 entradas)
- 📉 Controle de requisições com `--rpm` e `--throttle`
- 📁 Estrutura de saída organizada por domínio
- ✅ Verificação de dependências com `--check`

---

## 🚀 Uso

```bash
python3 bughuntbr.py [opções]
```

### 📌 Exemplo de execução completa:
```bash
python3 bughuntbr.py --target teste.com --scan --xss --nuclei --idor --tokenscan --quick --rpm 10 --throttle 2.0
```

---

## ⚙️ Opções

| Flag               | Descrição                                                  |
|--------------------|------------------------------------------------------------|
| `--target, -d`     | Domínio alvo (ex: `example.com`)                            |
| `--target-file, -tf` | Arquivo com lista de domínios (um por linha)             |
| `--output, -o`     | Diretório de saída (default: `bughunt_output`)             |
| `--scan`           | Executa reconhecimento completo                            |
| `--xss`            | Testa XSS com payloads usando Dalfox                       |
| `--idor`           | Busca padrões comuns de IDOR                               |
| `--tokenscan`      | Busca tokens ou segredos expostos                          |
| `--nuclei`         | Executa Nuclei nos hosts ativos                            |
| `--quick`          | Limita cada fase a 5 entradas para testes rápidos          |
| `--rpm`            | Limite de requisições por minuto (ex: `--rpm 50`)         |
| `--throttle`       | Delay entre comandos que fazem requisições (ex: `1.5s`)    |
| `--check`          | Instala automaticamente as dependências via Go             |

---

## 🛠️ Ferramentas exigidas

- `subfinder`
- `httpx`
- `gau`
- `waybackurls`
- `gospider`
- `qsreplace`
- `dalfox`
- `nuclei`

### 📦 Instale com:
```bash
go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest
go install github.com/lc/gau@latest
go install github.com/tomnomnom/waybackurls@latest
go install github.com/jaeles-project/gospider@latest
go install github.com/tomnomnom/qsreplace@latest
go install github.com/hahwul/dalfox/v2@latest
go install -v github.com/projectdiscovery/nuclei/v2/cmd/nuclei@latest
```
ou
python3 bughuntbr.py --check
| `--check`          | Instala automaticamente as dependências via Go             |
---

## 📁 Estrutura de saída

```
bughunt_output/
└── example.com/
    ├── subdomains.txt
    ├── hosts.txt
    ├── urls.txt
    ├── xss_<payload>.txt
    ├── idor.txt
    ├── tokens.txt
    ├── nuclei_results.txt
    └── executado_em.txt
```

---

## 🙌 Contribua

Pull requests são bem-vindos! Se encontrar bugs ou quiser propor melhorias, sinta-se à vontade para abrir uma issue.

---

## 📜 Licença

Este projeto é distribuído sob a licença MIT. 

### ❤️ Créditos

Desenvolvido por Solon Barroso, para bug bounty hunters.  
Contribuições são bem-vindas!

---
