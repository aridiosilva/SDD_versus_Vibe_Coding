<img width="540" height="360" alt="imagem-artigo_vibe-coding_versus_SSD" src="https://github.com/user-attachments/assets/d2ce76f1-864f-4dc0-a306-0571e7a779b7" />

# Spec-Driven Development vs. Vibe Coding

## Spec-Driven Development (SDD)

### Princípios
- Especificação (requisitos, contratos de API, casos de uso) é escrita e validada *antes* do código
- A IA (ou o dev) gera código a partir de specs formais/semiformais, muitas vezes com ciclo de revisão da spec antes de qualquer implementação
- Rastreabilidade: cada trecho de código deveria remontar a um requisito documentado
- Specs funcionam como "fonte da verdade", versionadas junto com o código

### Pontos fortes
- Alinhamento entre stakeholders antes de gastar esforço de implementação
- Facilita auditoria, compliance e governança (forte conexão com GRC)
- Reduz retrabalho por mal-entendidos de requisitos
- Specs viram documentação viva e testes de aceitação naturais
- Melhor para sistemas críticos, integrações complexas, times grandes

### Pontos fracos
- Overhead de tempo/esforço para escrever specs, especialmente em protótipos ou exploração
- Risco de "paralisia por especificação" — spec detalhada demais atrasa entrega
- Specs podem ficar desatualizadas se não houver disciplina de manutenção
- Menos ágil para descoberta de requisitos ainda incertos (produto novo, MVP)

## Vibe Coding (ad hoc, prompt-driven)

### Princípios
- Iteração rápida via prompts soltos, sem spec formal prévia
- O "requisito" emerge conversacionalmente enquanto o código é gerado
- Feedback loop curto: rodar, ver o resultado, ajustar o prompt
- Confia na intuição do desenvolvedor e na capacidade do modelo de inferir intenção

### Pontos fortes
- Velocidade altíssima para protótipos, provas de conceito, exploração criativa
- Baixa barreira de entrada — não exige formalização prévia
- Ótimo quando os requisitos são genuinamente incertos e mudam a cada teste
- Reduz fricção cognitiva no início do processo

### Pontos fracos
- Rastreabilidade quase nula — difícil saber por que uma decisão de design foi tomada
- Risco alto de dívida técnica e inconsistência arquitetural
- Dificulta auditoria e compliance (problema sério em contextos de GRC/segurança)
- Escala mal em times grandes ou projetos de longa duração
- Tende a acumular "código zumbi" — trechos gerados que ninguém entende totalmente
- Testabilidade e segurança tendem a ficar em segundo plano

## Síntese prática

Muitos times adotam um híbrido: vibe coding para exploração inicial e protótipos descartáveis, migrando para SDD assim que o projeto define escopo real — especialmente em ambientes regulados, onde rastreabilidade de requisito→código é exigida por auditoria (algo que conecta diretamente com GRC). O critério prático costuma ser: quanto maior o custo de erro e mais stakeholders envolvidos, mais a balança pende para spec-driven.

---
# Pipeline: SDD (Spec-Driven Development) x Vibe Coding

## Vibe Coding

**Pipeline:** prompt → código → itera → aceita

- Otimiza para velocidade, com pouca ou nenhuma etapa de planejamento, favorecendo iteração rápida e flexibilidade.
- Não há fase de planejamento, documento de requisitos ou revisão de design — as decisões ficam registradas apenas no histórico do chat.
- **Bom para:** protótipos, exploração, scripts pontuais.
- **Risco:** conforme o projeto cresce, estudos apontam taxas de vulnerabilidade em torno de 45% e desenvolvedores até 19% mais lentos em bases de código pesadas em IA.

## Spec-Driven Development (SDD)

**Pipeline (4 fases):** Specify → Plan → Implement → Verify
(equivalente também descrito como: specification → design → task plan → implementation → verification)

- Uma especificação formal, legível por máquina, é a fonte de verdade autoritativa, e o código, os testes e a documentação são derivados dela.
- Quando a realidade diverge da spec, corrige-se a spec e regenera-se o código — não o contrário.
- **Bom para:** produção, times, sistemas de longa duração.

## Diferença estrutural central

No vibe coding, o chat é a única fonte de registro; no SDD, um plano estruturado é a fonte de verdade, e o código é a saída "compilada" a partir dele.

## Síntese prática recomendada

Combinar exploração estruturada com specs vivas: vibe-codar para descobrir requisitos, depois formalizá-los em especificações versionadas antes do deploy em produção.

## Tabela comparativa

| Critério | Vibe Coding | SDD |
|---|---|---|
| Fonte de verdade | Chat/prompt | Spec versionada |
| Velocidade inicial | Alta | Menor (overhead upfront) |
| Manutenibilidade | Baixa em escala | Alta |
| Uso ideal | Protótipo/MVP | Produção/times |

## Ferramentas citadas para SDD

- GitHub Spec Kit
- AWS Kiro
- OpenSpec
- Tessl

---



#SpecDrivenDevelopment #VibeCoding #IA #EngenhariaDeSoftware #Produtividade #GRC #ArquiteturaDeSoftware #Inovação
