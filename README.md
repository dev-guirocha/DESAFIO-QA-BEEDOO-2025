Desafio QA Beedoo 2025

Autor: Guilherme Rocha
Função: Analista de Qualidade (QA)

Este repositório contém a análise e execução do desafio técnico proposto para a vaga de QA, com foco no módulo de gerenciamento de cursos da plataforma Beedoo.

🎯 Objetivo do Desafio

Avaliar a qualidade funcional e comportamental do fluxo de gerenciamento de cursos—especialmente os processos de criação e exclusão—considerando usabilidade, validação de dados, consistência visual e conformidade com regras de negócio.

🧭 Abordagem e Metodologia

A condução do teste foi baseada nos pilares abaixo:

Pilar	Descrição	Resultado
Análise Funcional	Identificar o que o usuário Administrador deve conseguir realizar.	Definição das ações principais: Cadastrar, Listar e Excluir cursos.
Requisitos Esperados	Verificar o que o sistema deveria garantir em termos de validações e regras de negócio.	Regras de validação identificadas e comparadas com o comportamento real.
Comportamento Real	Observar o sistema em funcionamento para detectar inconsistências.	Levantamento de bugs funcionais, validações e UI.

A partir dessa análise, foram elaboradas 3 User Stories que guiaram todo o ciclo de testes:

User Stories
	•	US-01 — Cadastro de Curso: Como Administrador, quero cadastrar um curso preenchendo corretamente suas informações, para disponibilizá-lo na plataforma.
	•	US-02 — Exclusão de Curso: Como Administrador, quero excluir um curso existente, para removê-lo da listagem de cursos.
	•	US-03 — Consistência Visual: Como Administrador, quero visualizar os cursos em um layout organizado e padronizado, para facilitar o gerenciamento.

Com base nessas histórias, foram criados 10 casos de teste, incluindo cenários positivos e negativos.

⸻

🐞 Principais Bugs Identificados

Foram encontrados problemas que variam de falhas críticas de funcionalidade a inconsistências na interface. Seguem os destaques:

Bugs Críticos (Funcionalidade / Lógica de Negócio)

Código	Descrição	Impacto
CT-007 + CT-009	A funcionalidade de Excluir Curso exibe mensagem de sucesso, mas não remove o curso. A análise revelou erro HTTP 405 na requisição à API.	Crítico — Fluxo principal comprometido.
CT-002	Cadastro permitido sem preenchimento mínimo dos campos (gera “curso fantasma”).	Crítico — Falha de validação essencial.
CT-004 / CT-005	Aceita valores inválidos (ex: vagas negativas, datas invertidas).	Alto — Quebra de regra de negócio.

Bugs de Validação de Dados
	•	Campos de texto permitem inserção numérica sem restrição (CT-003 e CT-006).

Bugs de Interface (UI) e Acessibilidade (A11y)
	•	CT-008: Cards dos cursos sem padronização de altura → layout desalinhado.
	•	CT-010: Uso incorreto de <button disabled> para textos informativos → prejudica leitores de tela e semântica HTML.

⸻

📂 Artefatos de Teste

Artefato	Link
Planilha de Casos de Teste (Google Sheets)	https://docs.google.com/spreadsheets/d/1Ojd4Mhcpsxi3Scnu4TTOhGCKP01pLlrfVLMPte4IxMw/edit?usp=sharing
Evidências (Vídeos + Capturas de Tela)	https://drive.google.com/drive/folders/12kjPpvUfrfhQ5DvafaUYYveL2aYBQ0_C?usp=share_link


⸻

🛠️ Ferramentas Utilizadas
	•	Teste e Gerenciamento: Google Sheets
	•	Versão e Documentação: Git & GitHub
	•	Gravação de Evidências: QuickTime Player + CloudConvert
	•	Análise Técnica / Debug: Chrome DevTools (Console, Network, Elements)

⸻

✅ Conclusão

O módulo testado apresenta fragilidades significativas em validação de dados, integridade de regras de negócio e comunicação com o back-end. Apesar disso, o fluxo geral é coerente e oferece boa base para evolução.
A correção das falhas mapeadas deve priorizar:
	1.	Regras de validação no front-end e back-end
	2.	Correção da rota de exclusão
	3.	Ajustes de UI e acessibilidade para melhor experiência de uso
