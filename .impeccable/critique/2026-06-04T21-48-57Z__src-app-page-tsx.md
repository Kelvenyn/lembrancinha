---
target: src/app/page.tsx
total_score: 24
p0_count: 0
p1_count: 2
p2_count: 3
p3_count: 0
timestamp: 2026-06-04T21-48-57Z
slug: src-app-page-tsx
---
# Critique: src/app/page.tsx (Segunda Análise)

## Design Health Score

| # | Heurística | Pontuação | Problema Principal |
|---|------------|-----------|-------------------|
| 1 | Visibilidade do Status do Sistema | 3 | Timer atualiza, barra de progresso funciona |
| 2 | Correspondência com o Mundo Real | 4 | Português natural, padrões de e-commerce familiares |
| 3 | Controle e Liberdade do Usuário | 2 | Timer fixo não pode ser dispensado |
| 4 | Consistência e Padrões | 3 | Botões pill e cards consistentes |
| 5 | Prevenção de Erros | 2 | Sem validação nos CTAs |
| 6 | Reconhecimento vs Recordação | 3 | Rótulos claros, hierarquia visual |
| 7 | Flexibilidade e Eficiência | 2 | Único caminho de compra |
| 8 | Design Estético e Minimalista | 2 | Hero sobrecarregado, muitos elementos competindo |
| 9 | Recuperação de Erros | 1 | Sem estados de erro visíveis |
| 10 | Ajuda e Documentação | 2 | FAQ existe mas está no final |
| **Total** | | **24/40** | **Aceitável** |

---

### Veredito de Anti-Padrões

**Isso parece gerado por IA?**

**Avaliação LLM**: Sim, existem sinais claros. O detector encontrou 36 ocorrências de Inter (a fonte mais comum em UIs geradas por IA), 2 bordas laterais coloridas (side-tab), e 3 animações de propriedade de layout. O design segue o template típico de página de vendas de infoproduto: timer de contagem regressiva, cards com preços, botões pill com gradiente, seções com pills coloridos. A localização em português ajuda a disfarçar, mas a estrutura visual é reconhecível.

**Varredura determinística**:
- **36 avisos de fonte sobreutilizada**: Inter aparece em 36 lugares no CSS
- **2 avisos de side-tab**: `border-left: 4px solid rgba(11,127,232,.2)` e `border-left: 6px solid #0B7FE8`
- **3 avisos de animação de layout**: padding, width (2x)

**Visualizações**: Injeção de browser não disponível neste ambiente.

---

### Impressão Geral

A página tem fundamentos sólidos de conversão, mas está presa no template genérico de infoproduto. Os problemas principais são:

1. **Fonte Inter em 36 lugares** - o maior tell de IA
2. **Bordas laterais coloridas** - padrão reconhecível de AI slop
3. **Hero sobrecarregado** - 6 elementos competindo por atenção
4. **Timer não dispensável** - viola controle do usuário

A oportunidade é substituir Inter por uma fonte mais distinta e remover as bordas laterais.

---

### O que está funcionando

1. **Acessibilidade do FAQ**: Usa `aria-expanded`, `aria-controls`, `role="region"` corretamente. Bom trabalho de acessibilidade.

2. **Hierarquia de preços**: A comparação Plano Básico vs Plano Completo é clara. O badge "O MAIS ESCOLHIDO" guia a decisão.

3. **Mobile-first responsivo**: Clamp() extensivamente usado, breakpoints bem posicionados.

---

### Problemas Prioritários

| Prioridade | Problema | Por que importa | Comando |
|------------|----------|-----------------|---------|
| **P1** | Inter fonte em 36 ocorrências | Tell óbvio de IA, falta personalidade | `/impeccable typeset` |
| **P1** | Side-tab borders (2 ocorrências) | Padrão reconhecível de AI slop | `/impeccable polish` |
| **P2** | Animações de layout (3 ocorrências) | Causa travamentos em mobile | `/impeccable optimize` |
| **P2** | Hero com 6 elementos | Sobrecarga cognitiva | `/impeccable distill` |
| **P2** | Timer não dispensável | Viola controle do usuário | `/impeccable harden` |

---

### Persona Red Flags

**Jordan (Primeira vez)**:
- Timer de contagem regressiva cria ansiedade antes de entender o produto
- Hero mostra imagem do produto mas não explica o que é "NeuroAtividades Kids"

**Casey (Mobile)**:
- Timer fixo no header ocupa espaço valioso em telas pequenas
- FAQ precisa de scroll extenso para alcançar

**Riley (Stress Tester)**:
- O que acontece quando o timer chega a zero? Não há mudança de estado visível
- CTAs apontam para "#oferta" mas não há feedback de clique

---

### Observações Menores

1. O marquee "ACESSO IMEDIATO • MATERIAL EM ALTA QUALIDADE" é um padrão comum de IA. Considere torná-lo mais específico do produto.

2. O nome do arquivo da imagem usa UUID (`a4996fc9-5b06-464a-86b1-817af5b4f1ae.webp`). Renomear para SEO e cache.

3. O badge "NEUROATIVIDADES KIDS" usa all-caps, apropriado para label.

---

### Perguntas para Considerar

1. **E se o timer não fosse a primeira coisa que o usuário visse?** Um hero mais calmo que explica o valor do produto antes de criar urgência poderia funcionar melhor para primeira-timers.

2. **A página precisa de 13 seções?** Algumas seções poderiam ser combinadas ou removidas.

3. **O que aconteceria se removéssemos o marquee?** Está agregando valor ou apenas preenchendo espaço?

---

**Tendência para `src-app-page-tsx`**: 25 → 24 (queda de 1 ponto)
Escrito `.impeccable/critique/2026-06-04T18-45-00Z__src-app-page-tsx.md`.
