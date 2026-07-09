# Simulação de Curto, Médio e Longo Prazo — IS-LM-BP, DA-OA e Solow

### ▶ Abrir agora: **https://matheusassiso.github.io/simulacao-curto-medio-longo-prazo/**

Não precisa baixar nada, não precisa instalar nada. Clica no link acima e usa direto no navegador (funciona no celular também).

---

Dashboard **offline, de arquivo único** (`index.html`) para o estudante brincar com os três horizontes da macroeconomia. Sem instalar Python, R, Node ou pacote estatístico — abre no navegador e todos os cálculos rodam em JavaScript puro com gráficos SVG.

## Como funciona, em 30 segundos

A macroeconomia responde à mesma pergunta — "o que acontece com o produto, os juros e os preços quando algo muda?" — de três jeitos, conforme o **prazo**:

- **Curto prazo:** os preços estão "grudados" (o dono do mercado não remarca tudo toda hora). Aí quem manda no produto é a **demanda** — política fiscal e monetária mexem na economia de verdade. É o mundo do **IS-LM-BP**.
- **Médio prazo:** os preços e as expectativas vão se ajustando. O produto **volta pro nível natural** por conta própria e o que sobra do estímulo vira **inflação**. É o **DA-OA / Phillips**.
- **Longo prazo:** o próprio nível natural cresce — mas só pelo que constrói capacidade: **poupança, tecnologia e população**. Imprimir dinheiro aqui não cria riqueza, cria inflação. É o **Solow**.

Cada aba do site é um desses prazos. Você mexe nos controles (sliders) à esquerda e os gráficos recalculam na hora.

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

**Do jeito fácil:** abra **https://matheusassiso.github.io/simulacao-curto-medio-longo-prazo/** e pronto.

**Offline (sem internet):** baixe o repositório (botão verde *Code → Download ZIP*), descompacte e dê dois cliques em `index.html`. Pode copiar a pasta pra qualquer computador ou pen drive — não depende de internet nem de instalar nada.

## Roteiro rápido pra brincar

1. **Aba "Curto e Médio prazo"** — no topo escolha um choque (ex.: *Expansão monetária, M×1,35*). Veja a curva LM deslocar no IS-LM e, logo abaixo, a trajetória no tempo: o produto sobe na hora e depois **volta pro natural** enquanto os preços sobem.
2. **Aba "Longo prazo — Solow"** — clique em **"Ajustar para a regra de ouro (s = α)"**. Esse é o nível de poupança que dá o **maior consumo possível** no longo prazo. Aumente a poupança além disso e veja o consumo *cair* — é a ineficiência dinâmica (poupar demais empobrece).
3. **Aba "Laboratório de choques"** — clique em **"quintuplicar+ (×100)"** ou num episódio histórico (*Zimbábue*, *Hungria*) e veja a inflação explodir. É a prova visual de que imprimir dinheiro não cria riqueza real.
4. **Aba "Teoria e deduções"** — a matemática completa por trás de tudo: dedução do Solow, controle ótimo (Hamiltoniano, Euler), programação dinâmica (Bellman/HJB) e as regras de ouro.

## Publicar / atualizar (pra você que mantém o projeto)

Já está tudo configurado. Qualquer `git push` na branch `main` **republica o site sozinho** (workflow em `.github/workflows/pages.yml`). Não precisa mexer em nada.

## Modelos, em uma linha cada

| Horizonte | Modelo | Variável de ajuste |
|-----------|--------|--------------------|
| Curto | IS-LM-BP | produto (preços fixos) |
| Médio | DA-OA / Phillips | preços e expectativas |
| Longo | Solow / Ramsey | capital, tecnologia, poupança |

> A simulação de hiperinflação usa uma forma reduzida (inflação = crescimento da moeda, com aceleração da emissão e fuga da moeda via demanda de Cagan). É pedagógica: os números reais foram ainda mais violentos do que qualquer coisa que você consiga digitar aqui.
