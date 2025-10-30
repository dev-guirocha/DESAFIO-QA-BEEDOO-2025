⸻

Desafio QA Beedoo 2025

Autor: Guilherme Rocha
Função: Analista de Qualidade (QA)

Este repositório contém a análise e execução do desafio técnico para o módulo de gerenciamento de cursos da plataforma Beedoo.

⸻

🎯 Objetivo do Desafio

Avaliar o fluxo de criação e exclusão de cursos, verificando:
	•	Comportamento funcional esperado
	•	Regras de validação de dados
	•	Consistência visual do módulo
	•	Conformidade com regras de negócio

⸻

🧭 Abordagem e Metodologia

Minha estratégia foi baseada em três etapas principais:
	1.	Análise Funcional
Identifiquei quais ações o usuário Administrador deveria executar (Cadastrar, Listar e Excluir cursos).
	2.	Requisitos Esperados
Determinei o que seria considerado um comportamento correto do sistema, como a validação de campos e a aplicação de regras de negócio.
	3.	Avaliação do Comportamento Real
Executei o fluxo real na plataforma, comparando o esperado com o observado e registrando inconsistências.

Com base nessas análises, elaborei as seguintes User Stories:
	•	US-01 — Cadastro de Curso: O Administrador deve conseguir cadastrar um novo curso preenchendo suas informações corretamente.
	•	US-02 — Exclusão de Curso: O Administrador deve conseguir excluir cursos existentes para que deixem de ser exibidos.
	•	US-03 — Consistência Visual: A lista de cursos deve ser exibida de forma organizada e padronizada, facilitando a visualização e o gerenciamento.

A partir dessas histórias, foram criados 10 casos de teste contemplando cenários positivos e negativos.

⸻

🐞 Principais Bugs Identificados

1. Falhas Críticas de Funcionalidade ou Lógica
	•	Exclusão de Curso não funcional: A plataforma exibe mensagem de sucesso ao excluir, porém o curso permanece na lista. A análise técnica apontou um erro de API (HTTP 405), indicando falha na rota de exclusão.
	•	Cadastro sem validações obrigatórias: É possível cadastrar um curso com campos completamente vazios, resultando em itens “fantasmas”.
	•	Violação de regras de negócio: O sistema aceita dados inválidos, como:
	•	número de vagas negativo
	•	datas onde a data de término é anterior à de início

2. Falhas de Validação de Dados
	•	Campos como Nome do Curso e Instrutor aceitam valores numéricos, sem validação de tipo ou padrão mínimo.

3. Problemas de Interface e Acessibilidade
	•	Altura dos cards de cursos não é padronizada, causando desalinhamento visual.
	•	Texto informativo está sendo renderizado dentro de botões desabilitados (<button disabled>), o que prejudica a semântica e leitores de tela (acessibilidade).

⸻

📂 Artefatos de Teste
	•	Planilha de Casos de Teste:
https://docs.google.com/spreadsheets/d/1Ojd4Mhcpsxi3Scnu4TTOhGCKP01pLlrfVLMPte4IxMw/edit?usp=sharing
	•	Evidências (vídeos e prints):
https://drive.google.com/drive/folders/12kjPpvUfrfhQ5DvafaUYYveL2aYBQ0_C?usp=share_link

⸻

🛠️ Ferramentas Utilizadas
	•	Google Sheets (gerenciamento de testes)
	•	Git & GitHub (versão e documentação)
	•	Google Drive (armazenamento de evidências)
	•	QuickTime Player + CloudConvert (gravação e conversão de vídeos)
	•	Chrome DevTools (inspeção de rede, console e estrutura HTML/CSS)

⸻

✅ Conclusão

O módulo testado apresenta problemas relevantes relacionados a validação de dados, aplicação de regras de negócio e comunicação com o back-end. Os ajustes prioritários devem focar na correção do endpoint de exclusão, implementação de regras de validação e melhoria da estrutura visual e semântica dos componentes.
