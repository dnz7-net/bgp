# Modelo BGP de Borda — Huawei VRP8

Modelo de referência de configuração BGP de borda para **Huawei VRP8 (V800R021C10)**:
2 trânsitos + route servers de IX, dual-stack, filtros no modelo tradicional (`route-policy`).

Site: `(https://dnz7-net.github.io/bgp/)`

## Conteúdo

| Caminho | O que é |
|---|---|
| `index.html` | Site de referência: parâmetros editáveis, syntax highlight, busca, cópia por seção e runbook |
| `configs/bgp-modelo-ideal-vrp8.cfg` | Configuração completa em texto, na ordem de build |
| `.nojekyll` | Faz o GitHub Pages servir os arquivos como estão, sem processar com Jekyll |

## Ordem de build

1. Global (`bfd`)
2. Prefix-lists IPv4
3. Prefix-lists IPv6
4. AS-path filters
5. Community filters
6. Route-policies base
7. Route-policies — trânsito A
8. Route-policies — trânsito B
9. Route-policies — IX route servers
10. Âncoras de originação (NULL0)
11. BGP — peers e sessão
12. BGP — aplicação por address-family
13. RPKI / ROV (opcional)



1. **Settings → Pages**
2. **Source:** *Deploy from a branch*
3. **Branch:** `main` / pasta `/ (root)` → **Save**
4. Aguarde 1 a 2 minutos. A URL aparece no topo da página de configuração do Pages.
