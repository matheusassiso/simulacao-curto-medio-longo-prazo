# Simulação de Curto, Médio e Longo Prazo — IS-LM-BP, DA-OA e Solow

Dashboard **offline, de arquivo único** (`index.html`) para o estudante brincar com os três horizontes da macroeconomia. Sem instalar Python, R, Node ou pacote estatístico — abre no navegador e todos os cálculos rodam em JavaScript puro com gráficos SVG.

## O que tem

**1. Curto e Médio prazo** — IS-LM-BP e DA-OA/Phillips
- Equilíbrio de curto prazo (preços fixos) e ajuste de médio prazo no tempo (preços e expectativas convergem, o produto volta ao natural).
- Choques prontos (fiscal, monetário, tributário, oferta) e todos os parâmetros ajustáveis.
- Tabela de multiplicadores calculados.

**2. Longo prazo — Solow**
- Equação fundamental `k̇ = s·f(k) − (n+g+δ)k`, estado estacionário, convergência no tempo.
- Diagrama de fase, série temporal de `k, y, c`, produto por trabalhador em escala log.
- **Regra de ouro** marcada no gráfico (botão "ajustar para s = α") e diagnóstico de ineficiência dinâmica.

**3. Laboratório de choques** — liberdade total
- Multiplique a base monetária por ×2, ×5, ×10, ×100 e veja neutralidade da moeda no extremo.
- Motor de hiperinflação: crescimento mensal da moeda + aceleração da emissão + fuga da moeda (η). Trajetória de preços em escala log e colapso dos saldos reais.
- Episódios históricos prontos (Hungria 1946, Zimbábue 2008, Iugoslávia 1994, Weimar, Grécia, Venezuela) e ranking das maiores hiperinflações.

**4. Teoria e deduções** (texto completo, em português)
- Dedução completa do modelo de Solow.
- Regra de ouro do capital.
- **Controle ótimo** (Ramsey-Cass-Koopmans): Hamiltoniano, princípio do máximo, equação de Euler / Keynes-Ramsey, regra de ouro modificada.
- **Programação dinâmica**: princípio de Bellman, equação de Hamilton-Jacobi-Bellman e a ponte `V'(k) = λ` entre os dois métodos.
- Modelo de Cagan da hiperinflação.

## Como usar

Abra `index.html` no navegador. Só isso. Copie a pasta para qualquer computador — funciona sem internet.

## Publicar no GitHub Pages

`push` na branch `main`; o workflow em `.github/workflows/pages.yml` publica a pasta inteira. Em *Settings → Pages*, defina a origem como **GitHub Actions**.

## Modelos, em uma linha cada

| Horizonte | Modelo | Variável de ajuste |
|-----------|--------|--------------------|
| Curto | IS-LM-BP | produto (preços fixos) |
| Médio | DA-OA / Phillips | preços e expectativas |
| Longo | Solow / Ramsey | capital, tecnologia, poupança |

> A simulação de hiperinflação usa uma forma reduzida (inflação = crescimento da moeda, com aceleração da emissão e fuga da moeda via demanda de Cagan). É pedagógica: os números reais foram ainda mais violentos do que qualquer coisa que você consiga digitar aqui.
