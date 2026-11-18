# Simulação de Curto, Médio e Longo Prazo — IS-LM-BP, DA-OA e Solow

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

## Abrir o HTML no navegador

[Baixe o ZIP do repositório](https://github.com/matheusassiso/simulacao-curto-medio-longo-prazo/archive/refs/heads/main.zip), extraia o conteúdo e abra [`index.html`](index.html) no navegador.

## Roteiro rápido pra brincar

1. **Aba "Curto e Médio prazo"** — no topo escolha um choque (ex.: *Expansão monetária, M×1,35*). Veja a curva LM deslocar no IS-LM e, logo abaixo, a trajetória no tempo: o produto sobe na hora e depois **volta pro natural** enquanto os preços sobem.
2. **Aba "Longo prazo — Solow"** — clique em **"Ajustar para a regra de ouro (s = α)"**. Esse é o nível de poupança que dá o **maior consumo possível** no longo prazo. Aumente a poupança além disso e veja o consumo *cair* — é a ineficiência dinâmica (poupar demais empobrece).
3. **Aba "Laboratório de choques"** — clique em **"quintuplicar+ (×100)"** ou num episódio histórico (*Zimbábue*, *Hungria*) e veja a inflação explodir. É a prova visual de que imprimir dinheiro não cria riqueza real.
4. **Aba "Teoria e deduções"** — a matemática completa por trás de tudo: dedução do Solow, controle ótimo (Hamiltoniano, Euler), programação dinâmica (Bellman/HJB) e as regras de ouro.

## Modelos, em uma linha cada

| Horizonte | Modelo | Variável de ajuste |
|-----------|--------|--------------------|
| Curto | IS-LM-BP | produto (preços fixos) |
| Médio | DA-OA / Phillips | preços e expectativas |
| Longo | Solow / Ramsey | capital, tecnologia, poupança |

> A simulação de hiperinflação usa uma forma reduzida (inflação = crescimento da moeda, com aceleração da emissão e fuga da moeda via demanda de Cagan). É pedagógica: os números reais foram ainda mais violentos do que qualquer coisa que você consiga digitar aqui.


## Teoria e deduções do simulador

### 1. Solow: dedução completa

Função de produção com tecnologia aumentadora de trabalho (Harrod-neutra), retornos constantes de escala:

> Y = K<sup>α</sup> (A·L)<sup>1−α</sup>, 0 < α < 1

Defina variáveis **por unidade de trabalho eficiente**: k = K/(AL), y = Y/(AL). Dividindo por AL:

> y = k<sup>α</sup> = f(k), f'(k) = α k<sup>α−1</sup> > 0, f''(k) < 0 (rendimentos decrescentes)

A população cresce a n (L̇/L = n) e a tecnologia a g (Ȧ/A = g). O capital acumula com poupança s e deprecia a δ:

> K̇ = s·Y − δK

Derivando k = K/(AL) no tempo (regra do produto) e substituindo, chega-se à **equação fundamental de Solow**:

> k̇ = s·f(k) − (n + g + δ)·k

O termo s·f(k) é o investimento efetivo por unidade eficiente; (n+g+δ)k é o "investimento de reposição" necessário para manter k constante (repor depreciação δ, equipar novos trabalhadores n e acompanhar a maior eficiência g).

##### Estado estacionário (k̇ = 0)

> s·f(k*) = (n+g+δ)·k* ⇒ k* = [ s / (n+g+δ) ]<sup>1/(1−α)</sup>

> y* = k*<sup>α</sup>, c* = (1−s)·y*

**Convergência:** como f é côncava, se k < k* então k̇ > 0 (a economia cresce até k*); se k > k*, k̇ < 0. O estado estacionário é estável. Fora dele estamos no "curto/médio prazo" da transição; nele, na *senda de crescimento equilibrado* (longo prazo): Y/L cresce a g, Y cresce a n+g, e Y/K é constante.

### 2. Regra de ouro do capital

Qual taxa de poupança maximiza o consumo de estado estacionário? Substituindo k* em c* = f(k*) − (n+g+δ)k*, maximizamos em k*:

> dc*/dk* = f'(k<sub>ouro</sub>) − (n+g+δ) = 0 ⇒ f'(k<sub>ouro</sub>) = n + g + δ

Ou seja, a **produtividade marginal do capital líquida de depreciação iguala n+g**: PMgK − δ = n + g. Para Cobb-Douglas, f'(k)=α k<sup>α−1</sup>, isso dá a taxa de poupança de ouro:

> s<sub>ouro</sub> = α (a participação do capital na renda)

- **s > α:** ineficiência dinâmica — poupa-se demais; é possível consumir mais *hoje e sempre* reduzindo a poupança (Pareto-melhora sem custo).
- **s < α:** poupa-se de menos para o consumo máximo de longo prazo, mas aumentar s custa consumo no presente — há um trade-off intertemporal real.

### 3. Controle ótimo: o modelo de Ramsey-Cass-Koopmans

Solow supõe s constante e exógeno. Ramsey deixa a *poupança ser escolhida* por um planejador (ou famílias) que maximiza o bem-estar. Problema de controle ótimo em tempo contínuo — estado k, controle c:

> max<sub>c(t)</sub> ∫<sub>0</sub><sup>∞</sup> e<sup>−ρt</sup> u(c) dt s.a. k̇ = f(k) − c − (n+g+δ)k, k(0)=k₀

com utilidade CRRA: u(c) = (c<sup>1−θ</sup> − 1)/(1−θ), onde θ é a aversão relativa ao risco / inverso da elasticidade de substituição intertemporal, e ρ > 0 é a taxa de desconto.

##### Hamiltoniano de valor presente

> H = e<sup>−ρt</sup> u(c) + μ·[ f(k) − c − (n+g+δ)k ]

Usando o Hamiltoniano de valor corrente Ĥ = u(c) + λ[f(k)−c−(n+g+δ)k] com λ = μe<sup>ρt</sup>, as **condições de primeira ordem** (princípio do máximo de Pontryagin) são:

> (i) ∂Ĥ/∂c = 0 ⇒ u'(c) = λ

> (ii) λ̇ = ρλ − ∂Ĥ/∂k = λ[ ρ + (n+g+δ) − f'(k) ]

> (iii) condição de transversalidade: lim<sub>t→∞</sub> e<sup>−ρt</sup> λ k = 0

Derivando (i) no tempo (u''(c)ċ = λ̇) e combinando com (ii), obtém-se a **equação de Euler / regra de Keynes-Ramsey**:

> ċ/c = (1/θ) · [ f'(k) − δ − ρ − θg ]

Interpretação: o consumo cresce quando o retorno do capital (f'(k)−δ) supera a impaciência ajustada (ρ+θg). Se poupar rende mais que a pressa em consumir, adia-se o consumo.

##### Regra de ouro modificada

No estado estacionário do Ramsey, ċ = 0, logo:

> f'(k**) − δ = ρ + θg ⇒ f'(k**) = ρ + δ + θg

Compare com a regra de ouro pura (f'=n+g+δ, i.e. f'−δ=n+g). Como em equilíbrio dinâmico ρ > n+(1−θ)g (para a integral convergir), tem-se ρ+θg > n+g, portanto **f'(k**) > f'(k<sub>ouro</sub>)** e, por concavidade, **k** < k<sub>ouro</sub>**. O ótimo poupa *menos* que a regra de ouro: descontar o futuro (ρ) torna irracional sacrificar consumo presente até o máximo de longo prazo. A economia de Ramsey nunca é dinamicamente ineficiente.

### 4. Programação dinâmica: Bellman e a HJB

O mesmo problema resolvido por programação dinâmica. Defina a **função valor** — o bem-estar máximo alcançável partindo do capital k:

> V(k) = max<sub>c(·)</sub> ∫<sub>0</sub><sup>∞</sup> e<sup>−ρt</sup> u(c) dt s.a. k̇ = f(k) − c − (n+g+δ)k

O **princípio da otimalidade** de Bellman diz que uma política ótima tem a propriedade de que, seja qual for o estado inicial e a primeira decisão, as decisões restantes formam uma política ótima a partir do novo estado. Em tempo discreto (passo Δ):

> V(k) = max<sub>c</sub> { u(c)·Δ + e<sup>−ρΔ</sup> V(k + k̇·Δ) }

Expandindo e<sup>−ρΔ</sup> ≈ 1−ρΔ e V(k+k̇Δ) ≈ V(k)+V'(k)k̇Δ, dividindo por Δ e fazendo Δ→0, chega-se à **equação de Hamilton-Jacobi-Bellman (HJB)**:

> ρ V(k) = max<sub>c</sub> { u(c) + V'(k)·[ f(k) − c − (n+g+δ)k ] }

A condição de primeira ordem interna dá a **ponte entre os dois métodos** — a derivada da função valor *é* o co-estado do controle ótimo:

> u'(c) = V'(k) = λ (o preço-sombra do capital)

Diferenciando a HJB em k recupera-se exatamente a equação de Euler acima. Controle ótimo (Pontryagin) e programação dinâmica (Bellman) descrevem a mesma solução: um dá a trajetória (condições necessárias ao longo do tempo), o outro dá a *regra de decisão* c = c(k) (política ótima como função do estado).

### 5. Como os três horizontes se conversam

- **Curto prazo (IS-LM-BP):** preços rígidos, expectativas dadas. Moeda e política fiscal movem o produto real. É a aba *Curto e Médio prazo*, gráfico IS-LM.
- **Médio prazo (DA-OA / Phillips):** preços e expectativas se ajustam; o produto retorna ao natural Yn e o que sobra do choque monetário vira inflação. É a simulação temporal daquela aba.
- **Longo prazo (Solow / Ramsey):** o próprio Yn cresce pela acumulação de capital e progresso técnico. A moeda é neutra; o que importa são poupança, tecnologia e demografia. É a aba *Solow*.

A **neutralidade da moeda no longo prazo** é o fio condutor do laboratório de choques: quintuplicar M não cria riqueza real permanente — cria inflação. No limite patológico (Cagan), a fuga da moeda realimenta a alta e produz as hiperinflações históricas da tabela.

### 6. Modelo de Cagan (hiperinflação)

Demanda por moeda que depende só da inflação esperada (nas hiperinflações a renda real é secundária), em logaritmos:

> m<sub>t</sub> − p<sub>t</sub> = −η · π<sup>e</sup><sub>t</sub> (η > 0 = semi-elasticidade)

Resolvendo para o nível de preços: p<sub>t</sub> = m<sub>t</sub> + η π<sup>e</sup><sub>t</sub>. Se a moeda cresce a μ e as expectativas são adaptativas (π<sup>e</sup> revisada por λ do erro), uma expectativa maior de inflação reduz a demanda por saldos reais, o que exige preços ainda mais altos — o laço de realimentação. Com previsão perfeita e μ crescente, p explode mesmo com m finito: é a moeda perdendo a função de reserva de valor. Ajuste μ, η e λ na aba de choques e observe o índice de preços em escala log.
