# Modelo BGP de Borda — Huawei VRP8

Modelo de referência de configuração BGP de borda para **Huawei VRP8 (V800R021C10)**:
2 trânsitos + route servers de IX, dual-stack, filtros no modelo tradicional (`route-policy`).

Site: `https://<seu-usuario>.github.io/bgp-borda-vrp8/`

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

## Avisos

- **Todos os valores são placeholders de documentação** (RFC 5398, 5737 e 3849). Eles colidem com os
  próprios filtros de bogon do modelo. Substitua todos antes de aplicar.
- **Nunca suba configuração real neste repositório.** Isso inclui IPs públicos de produção, hashes
  `%^%#` (cipher reversível), shared-keys de RADIUS, communities SNMP, usuários e ACLs de gerência.
  Um repositório público fica indexado e copiado por terceiros.
- Itens marcados `VALIDAR` dependem de release: confirme com `?` no CLI ou na documentação Huawei.
- Aplique em janela, com backup, um peer por vez e soft refresh (`refresh bgp ... import|export`).

## Publicar o site (GitHub Pages)

1. **Settings → Pages**
2. **Source:** *Deploy from a branch*
3. **Branch:** `main` / pasta `/ (root)` → **Save**
4. Aguarde 1 a 2 minutos. A URL aparece no topo da página de configuração do Pages.
