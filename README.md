# 🏅 Sistema de Gestão das Olimpíadas (SGO)

Trabalho da disciplina **Projeto de Software** — PUC Minas  
Professor: João Paulo Carneiro Aramuni  
Curso: Engenharia de Software — 4º Período

---

## 📋 Descrição do Sistema

O Sistema de Gestão das Olimpíadas (SGO) é uma plataforma desenvolvida para coordenar os diferentes aspectos do evento olímpico. O sistema permite o gerenciamento de competições, inscrições de atletas, alocação de locais para as provas e controle de resultados.

---

## 📖 Histórias de Usuário

### US01 — Cadastrar Competição
**Como** administrador do sistema,  
**Quero** cadastrar novas competições informando modalidade, data, horário e local,  
**Para que** as provas olímpicas sejam devidamente registradas e organizadas no sistema.

**Critérios de aceitação:**
- O sistema deve exigir nome da modalidade, data, horário e local
- O sistema deve validar se o local está disponível no horário escolhido
- O cadastro deve gerar um identificador único para a competição

---

### US02 — Editar Competição
**Como** administrador do sistema,  
**Quero** editar as informações de uma competição já cadastrada,  
**Para que** eventuais alterações de data, horário ou local sejam refletidas no sistema.

**Critérios de aceitação:**
- O sistema deve revalidar conflitos de horário ao alterar local ou horário
- Atletas inscritos devem ser notificados sobre alterações relevantes

---

### US03 — Inscrever Atleta em Competição
**Como** atleta,  
**Quero** me inscrever em uma competição específica representando meu país,  
**Para que** eu possa participar oficialmente da prova olímpica.

**Critérios de aceitação:**
- O atleta deve estar previamente cadastrado no sistema
- Cada atleta pode se inscrever em várias competições
- Um atleta só pode representar um país por modalidade
- O sistema deve impedir inscrições duplicadas na mesma modalidade com países diferentes

---

### US04 — Cancelar Inscrição
**Como** atleta,  
**Quero** cancelar minha inscrição em uma competição,  
**Para que** minha vaga seja liberada e o sistema seja atualizado corretamente.

**Critérios de aceitação:**
- O cancelamento só deve ser permitido até uma data-limite antes da prova
- O status da inscrição deve ser atualizado para "CANCELADA"

---

### US05 — Alocar Local para Competição
**Como** administrador,  
**Quero** alocar um local específico para uma competição,  
**Para que** os espaços físicos sejam utilizados sem conflito de horário.

**Critérios de aceitação:**
- O sistema deve verificar automaticamente se há conflito de horário no local solicitado
- Um local só pode abrigar uma competição por vez
- O sistema deve exibir uma mensagem de erro caso o local já esteja ocupado

---

### US06 — Verificar Disponibilidade de Local
**Como** administrador,  
**Quero** consultar a disponibilidade de um local em uma data e horário específicos,  
**Para que** eu possa planejar a alocação das competições com antecedência.

**Critérios de aceitação:**
- O sistema deve exibir todas as competições já alocadas em um local
- O sistema deve indicar claramente os horários disponíveis e ocupados

---

### US07 — Registrar Resultado de Competição
**Como** administrador,  
**Quero** registrar o resultado de uma competição finalizada, indicando os três primeiros colocados,  
**Para que** as medalhas sejam atribuídas corretamente.

**Critérios de aceitação:**
- O sistema deve exigir que a competição esteja com status "EM_ANDAMENTO" ou "FINALIZADA"
- Os três primeiros colocados devem ser atletas inscritos na competição
- O sistema deve gerar automaticamente as medalhas de ouro, prata e bronze

---

### US08 — Consultar Resultado de Competição
**Como** atleta ou membro do comitê olímpico,  
**Quero** consultar o resultado de uma competição,  
**Para que** eu possa verificar os classificados e as medalhas conquistadas.

**Critérios de aceitação:**
- O resultado deve estar visível assim que for registrado pelo administrador
- O sistema deve exibir nome do atleta, país e posição final

---

### US09 — Gerar Relatório de Medalhas
**Como** membro do Comitê Olímpico,  
**Quero** gerar um relatório de medalhas por país,  
**Para que** o desempenho de cada nação nas Olimpíadas seja acompanhado.

**Critérios de aceitação:**
- O relatório deve exibir a contagem de medalhas de ouro, prata e bronze por país
- O relatório deve ser ordenável por total de medalhas ou por tipo
- O sistema deve permitir a exportação do relatório em PDF ou Excel

---

### US10 — Cadastrar Atleta
**Como** administrador,  
**Quero** cadastrar um novo atleta no sistema informando seus dados pessoais e país de origem,  
**Para que** o atleta possa se inscrever em competições.

**Critérios de aceitação:**
- Os campos obrigatórios são: nome completo, data de nascimento, documento e país
- O sistema deve impedir o cadastro de atletas duplicados pelo documento

---

### US11 — Cadastrar Local
**Como** administrador,  
**Quero** cadastrar um novo local disponível para as competições,  
**Para que** ele possa ser alocado para as provas.

**Critérios de aceitação:**
- Os campos obrigatórios são: nome, endereço e capacidade
- O local deve estar disponível para alocação imediatamente após o cadastro

---

### US12 — Listar Competições
**Como** atleta, administrador ou membro do comitê,  
**Quero** visualizar a lista de todas as competições cadastradas com suas informações,  
**Para que** eu possa acompanhar a programação das Olimpíadas.

**Critérios de aceitação:**
- A listagem deve exibir modalidade, data, horário, local e status
- Deve ser possível filtrar por modalidade, data ou status

---

## 🗂️ Diagramas UML

### Diagrama de Caso de Uso

<img width="700px" src="./imagens/Diagrama de Caso de Uso.png"/>

---

### Diagrama de Classes

<img width="700px" src="./imagens/Diagrama de Classes.png"/>

---

### Diagrama de Pacotes

<img width="700px" src="./imagens/Diagrama de Componentes.png"/>

---

### Diagrama de Componentes

<img width="700px" src="./imagens/diagrama-de-componentes.png"/>

---

### Diagrama de Implantação

<img width="700px" src="./imagens/diagrama-de-implantacao.png"/>

---

---

## 📌 Regras de Negócio

1. **Cadastro de competições:** O sistema permite cadastrar competições com nome da modalidade, data, horário, local e lista de atletas inscritos.
2. **Inscrição de atletas:** Cada atleta pode participar de várias competições, mas só pode representar um país por modalidade.
3. **Alocação de locais:** Um local só pode abrigar uma competição por vez, evitando conflitos de horário.
4. **Controle de resultados:** Os resultados determinam o 1º, 2º e 3º lugares, gerando as respectivas medalhas.
5. **Relatórios de medalhas:** O sistema gera relatórios consolidados por país com base nas medalhas conquistadas.
