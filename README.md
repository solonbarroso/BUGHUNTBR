# BUGHUNTBR
Bug bounty com precisão e propósito

---

## 🐞 BugHuntBR — Reconhecimento para Bug Bounty

`BugHuntBR` é uma ferramenta ofensiva voltada para caçadores de vulnerabilidades em programas de Bug Bounty. Focada em automação com precisão e respeito ao escopo, ela oferece módulos potentes para análise de subdomínios, parâmetros, XSS, IDOR, tokens expostos e muito mais.

---

### 🧠 Funcionalidades

- 🔎 **Reconhecimento Completo**: subdomínios, hosts ativos, URLs históricas, crawling, análise de parâmetros.
- 🧪 **Testes de XSS**: com múltiplos payloads + Dalfox.
- 🕵️‍♂️ **Detector de IDOR**: variação automática de IDs e parâmetros sensíveis.
- 🛡️ **Scan com Nuclei**: CVEs, misconfigs, etc.
- 🔐 **Busca por Tokens/JWTs**: em URLs indexadas.
- ⚡ **Modo Rápido** (`--quick`): para desenvolvimento e testes rápidos.
- 📄 **Múltiplos Alvos com Lista** (`--target-file`).

---

### 📦 Instalação de Dependências

Use a flag `--check` para instalar todas as ferramentas automaticamente (requer Go):

```bash
./bughuntbr.py --check
```

---

### 🚀 Uso

```bash
./bughuntbr.py [OPÇÕES]
```

#### 🔹 Alvo único
```bash
./bughuntbr.py -d example.com --scan --xss --nuclei --idor --tokenscan
```

#### 🔹 Múltiplos alvos (arquivo `.txt`)
```bash
./bughuntbr.py -tf alvos.txt --scan --xss --nuclei
```

#### 🔹 Modo rápido para testes
```bash
./bughuntbr.py -d example.com --scan --quick
```

---

### ⚙️ Opções

| Flag              | Descrição |
|-------------------|-----------|
| `--target, -d`    | Domínio único |
| `--target-file, -tf` | Arquivo com domínios (1 por linha) |
| `--output, -o`    | Diretório de saída (default: `bughunt_output`) |
| `--scan`          | Reconhecimento completo |
| `--xss`           | Teste de XSS com qsreplace + dalfox |
| `--idor`          | Busca por IDOR |
| `--tokenscan`     | Detecta tokens expostos |
| `--nuclei`        | Executa Nuclei |
| `--quick`         | Limita a 5 entradas para testes rápidos |
| `--throttle`      | Delay entre requisições (ex: `--throttle 1.5`) |
| `--check`         | Instala ferramentas requeridas automaticamente |

---

### 📂 Estrutura de Saída

```
bughunt_output/
└── example.com/
    ├── subs.txt
    ├── hosts.txt
    ├── urls.txt
    ├── params_clean.txt
    ├── params_report.json
    ├── idor_findings.txt
    ├── token_exposed.txt
    ├── nuclei_results.txt
    └── xss_results/
```

---

### 💡 Requisitos

- Linux/macOS
- Go instalado
- Ferramentas: subfinder, httpx, gau, waybackurls, gospider, dalfox, nuclei, qsreplace

---

### ❤️ Créditos

Desenvolvido por Solon Barroso, para bug bounty hunters.  
Contribuições são bem-vindas!

---
