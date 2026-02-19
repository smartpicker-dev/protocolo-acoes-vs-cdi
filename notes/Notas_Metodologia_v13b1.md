# Notas internas — Capítulo 2 (Metodologia) — v13b1 / HOTFIX M1

**Status:** texto final do capítulo em `02_metodologia_v3.md` (após Hotfix M1)  
**Propósito destas notas:** registrar decisões editoriais e pontos de consistência/auditoria para manutenção do paper, sem alterar o conteúdo científico nem introduzir resultados.

## 1) Âncoras metodológicas (o que o capítulo precisa refletir)
- **Protocolo pré-registrado e congelado (v1.3; 14/02/2026).**
- **Snapshots (datas finais):**
  - D0 = 10/02/2026
  - D-6m = 08/08/2025 (ajuste por não-pregão/sem dado)
  - D-12m = 10/02/2025
- **Regra não-pregão/sem dado:** usar o último dia disponível anterior e registrar o ajuste.
- **Janelas fixas:** 5, 10, 15, 20 e 25 anos.
- **Carteiras:** A/B/C; 8 ações cada; pesos iguais no início; buy-and-hold; sem rebalanceamento; composição detalhada apenas no **Apêndice A**.
- **Benchmarks:** CDI, Ibovespa, S&P 500 em BRL (PR e TR).
- **Métricas:** retorno total acumulado (primária), CAGR; risco core (volatilidade anualizada, drawdown máximo, Sharpe/Sortino vs CDI); estatísticas mensais (quando reportadas/consistentes); robustez por snapshots (ranges e ranking).

## 2) Restrições editoriais aplicadas (Regras de Ouro)
- **Sem nomes de arquivos (CSV/ZIP/manifest/checksums) no corpo do capítulo.**
- **Evitar jargão técnico/inglês desnecessário no texto (ex.: “endpoint”, “bundle”, “sanity check”).**
- **Não usar “educacional” no Cap. 2.**
- **Não listar tickers no Cap. 2** (composição completa encaminhada ao Apêndice A).
- **Referências no corpo do paper:** apenas “Tabela X”, “Figura X”, “Apêndice A” (quando necessário).  
  (No Hotfix M1 final, o Cap. 2 não precisa citar Data Availability/replicação/capítulos.)

## 3) Decisões de redação (por quê)
- Troca de termos para manter linguagem paper-like em PT-BR:
  - “bundle” → “pacote”
  - “endpoint” → “ponto final da janela (data final do recorte)”
- Frases de cautela limitadas ao mínimo: 1 frase no início (não recomendação) e 1 frase final de escopo, sem remeter a outro capítulo.
- Estrutura mantida estável para evitar divergência com Cap. 3 (Resultados) e Cap. 4 (Discussão/Limitações/Conclusão).

## 4) Log do HOTFIX M1 (somente o que mudou)
> Objetivo: eliminar termos proibidos e referências indevidas, mantendo o texto idêntico fora dos trechos patchados.

- **2.2:** removida referência à seção de “Disponibilidade de dados e reprodutibilidade” no corpo do capítulo.
- **2.4.1:** “bundle” substituído por “pacote” na expressão “pacote congelado”.
- **2.6:** “endpoint” substituído por formulação em português (“ponto final da janela…”).
- **2.7:** removida menção a “documentados no pacote de replicação”; frase encurtada para “procedimentos de validação”.
- **2.8:** removida referência a “Capítulo 4”; substituída por cautela neutra “devem ser consideradas na leitura”.

## 5) Checklist rápido de consistência (para revisão final do paper)
- Cap. 3 deve:
  - manter as datas D0/D-6m/D-12m consistentes com o Cap. 2;
  - referenciar corretamente Figuras 3a/3b (evitar “Figura 3” genérica);
  - não introduzir tickers fora do Apêndice A (a menos que seja decisão editorial global).
- Cap. 4 deve:
  - conter a seção completa de Disponibilidade de dados e reprodutibilidade (para onde o Cap. 2 não aponta mais).
- Apêndice A deve:
  - conter a composição integral das carteiras e definição do universo efetivo.
- Verificar “higiene de termos”:
  - não reaparecer “bundle/endpoint/sanity check” em nenhum capítulo.

---

## Referência rápida: arquivo final do Cap. 2
- `02_metodologia_v3.md` (texto final após Hotfix M1)

