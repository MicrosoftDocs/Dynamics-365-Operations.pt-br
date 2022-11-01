---
title: Visão geral dos cursos
description: Este artigo explica como os administradores e gerentes de Recursos Humanos podem usar os recursos dos cursos para disponibilizar as informações para os funcionários.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a1fd00fb9feea9ab426f67095770389696452215
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/25/2022
ms.locfileid: "9716329"
---
# <a name="courses-overview"></a>Visão geral dos cursos

O Microsoft Dynamics 365 Human Resources fornece uma solução para as necessidades de aprendizagem da sua organização. Essa solução oferece dois caminhos de aprendizagem: *virtual* e *orientada por um instrutor*.

A opção de *ensino virtual* é uma experiência de aprendizagem enriquecida com recursos on-line. No *treinamento com instrutor*, uma pessoa guia a sessão de treinamento para um grupo de funcionários ou participantes.

No nosso módulo de treinamento, os profissionais de Recursos Humanos, administradores, organizadores e gerentes podem criar e definir os dois caminhos de aprendizagem para os funcionários.

> [!NOTE]
> Nos cursos virtuais, é preciso habilitar o recurso **Melhorias do curso** no gerenciamento de recursos.

## <a name="set-up-virtual-courses"></a>Configurar os cursos virtuais

Para configurar os cursos virtuais, é preciso habilitar o recurso **Melhorias do curso** no Gerenciamento de recursos. Acesse **Cursos \> Novo** e defina a opção **Virtual** como **Sim**. Depois que o recurso for habilitado, é necessário ter um link para o curso. O campo **Status do curso** será definido como **Aberto**. A opção **Permitir que o funcionário faça o autorregistro** será definida como **Sim**, mas pode ser alterada para **Não**.

Depois de habilitar o recurso **Melhorias do curso** no Gerenciamento de recursos, as seguintes mudanças vão ocorrer:

- Uma data de conclusão precisa ser definida para atribuição do curso.
- É preciso ter um link do curso.
- O campo **Autoatendimento para funcionários** mostrará uma visão geral em **Cursos**. O usuário pode ver os cursos que expiraram, que expiram em breve e que foram atribuídos.
- Os funcionários podem fazer os cursos virtuais e autoatestar a conclusão deles.

## <a name="set-up-instructor-led-courses"></a>Configurar cursos com instrutores

Os cursos com instrutores não precisam ser configurados.

As informações a seguir são informações opcionais e podem ser especificadas para os cursos. Se você for inserir estas informações para os cursos, será necessário realizar a configuração antes de criar os registros deles:

- Tipo de curso
- Grupos de salas de aula
- Grupos de cursos
- Locais do curso
- Salas de aula
- Instrutores
- Tipos de cursos

É possível usar os *tipos de cursos* para categorizá-los de acordo com a estrutura ou o conteúdo deles. Você pode criar os tipos de cursos na página  **Tipos de cursos** .

O número mínimo e máximo de participantes que você pode registrar em um curso é definido na FastTab  **Geral**  da página  **Cursos** .

### <a name="course-setup-type"></a>Tipo de configuração de curso 

A opção *Configurar tipos* determina a estrutura do curso. Há três tipos de configuração dos cursos.

| Tipo de instalação | Descrição |
|------|--------|
| Padrão | Cursos deste tipo de configuração não tem uma agenda diária. Este é o tipo de configuração padrão quando você cria um novo curso. |
| Agenda | Selecione este tipo de configuração para planejar os detalhes de cada dia de um curso que acontecerá em vários dias. |
| Agenda + sessão | <p>Selecione este tipo de configuração para os cursos mais complexos. Por exemplo, é possível dividir a agenda do curso em *trajetórias* e *sessões*.</p><ul><li>*Trajetórias* são as áreas específicas de um curso.</li><li>*Sessões* dividem as trajetórias e ajudam a identificar os processos ou as técnicas relevantes para uma trajetória.</li></ul> |

### <a name="course-tasks"></a>Tarefas do curso

Para cada curso, complete as seguintes tarefas:

- Registrar os participantes.
- Especificar um prazo final para registro.
- Definir o número mínimo e máximo de participantes.
- Atribuir um local para o curso e uma sala de aula.
- Recomendar hotéis aos participantes do curso.
- Criar uma descrição que possa ser anunciada no  **Autoatendimento para funcionários**.

> [!NOTE]
> Você só poderá excluir um curso se ninguém se registrar para ele.

### <a name="course-statuses"></a>Status do curso

A tabela a seguir lista os status do curso e as ações concluídas para cada um.

| Status | Ações |
|------|--------|
| Criado em | <ul><li>Inserir e modificar informações do curso.</li><li>Alterar o status do curso para  **Aberto** permitindo que os funcionários se registrem no curso.</li></ul> | 
| Abrir | <ul><li>Registrar participantes no curso.</li><li>Remover participantes do curso.</li><li>Confirmar participantes no curso.</li><li>Mudar o status do curso para  **Fechado**  ou  **Cancelado** para os participantes que tiverem o status  **Confirmado**.</li></ul>|
| Fechada | Você pode reabrir o curso. |
| Cancelado | Você pode reabrir o curso. |

### <a name="course-participants"></a>Participantes do curso

Os *participantes do curso* são os funcionários que participam de um curso ou evento de treinamento. Só é possível registrar participantes em cursos abertos.

### <a name="workflow"></a>Fluxo de Trabalho

Os funcionários que se registram em um curso na página  **Autoatendimento para funcionários**  podem ter o registro encaminhado para a aprovação em um fluxo de trabalho. É possível atribuir um fluxo de trabalho a um curso na FastTab  **Geral**  na página  **Cursos** .
