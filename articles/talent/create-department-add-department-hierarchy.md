---
title: "Criar um departamento e associá-lo à hierarquia de departamentos"
description: "Um departamento é uma unidade operacional que representa uma categoria ou uma área funcional de uma organização. Um departamento é responsável por uma área específica da organização, como vendas, contabilidade ou recursos humanos. Você pode usar departamentos para relatar áreas funcionais. Os departamentos podem ter a responsabilidade de lucros e perdas."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HierarchyDesigner, OMOperatingUnit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: cea3ecd66a57780c9ef1b3a3c21f1e5273faa0ef
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="create-a-department-and-associate-it-with-the-department-hierarchy"></a>Criar um departamento e associá-lo à hierarquia de departamentos

[!include[banner](includes/banner.md)]


Um departamento é uma unidade operacional que representa uma categoria ou uma área funcional de uma organização. Um departamento é responsável por uma área específica da organização, como vendas, contabilidade ou recursos humanos. Você pode usar departamentos para relatar áreas funcionais. Os departamentos podem ter a responsabilidade de lucros e perdas.

Um departamento pode incluir um grupo de centros de custo. As posições podem ser atribuídas aos departamentos. Para criar um departamento, clique em **Recursos Humanos** &gt; **Departamentos** &gt; **Departamento**. A tabela a seguir descreve os campos disponíveis.

| Campo               | Descrição                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nome                | Insira o nome para o departamento.                                                                                                                                                                                  |
| Número de departamento   | Um valor padrão poderá ser gerado automaticamente se um código de sequência numérica for atribuído à referência **Número da organização** na página **Sequências numéricas**.                                                 |
| Nome de pesquisa         | Insira um nome ou um acrônimo que possa ser usado para procurar o departamento.                                                                                                                                            |
| Memorando                | Insira quaisquer informações adicionais aqui.                                                                                                                                                                            |
| Na hierarquia        | Uma caixa de seleção marcada indica que o departamento está incluído na hierarquia de departamentos. Para obter informações sobre como adicionar um departamento à hierarquia de departamentos, consulte as informações posteriormente neste artigo. |
| Número de DUNS         | DUNS significa Data Universal Number System (número universal do sistema de numeração). Este é um número de nove dígitos que é emitido pela Dun & Bradstreet.                                                                                                     |
| Gerente             | Insira a persona que gerencia o departamento.                                                                                                                                                                    |
| Endereços           | Adicione as informações de endereço do departamento. Por exemplo, adicione o endereço para correspondência da compilação que o departamento está localizado.                                                                          |
| Informações do contato | Adicione as informações de contato do departamento. Por exemplo, adicione um número de telefone da mesa de serviço no departamento.                                                                                           |

Para adicionar um departamento à hierarquia de departamentos, siga estas etapas.

1.  Clique em **Recursos Humanos** &gt; **Departamentos** &gt; **Hierarquia de departamentos**.
2.  Clique em **Editar** e selecione a organização em que o departamento deve estar.
3.  Clique em**Inserir** e selecione **Departamento** na lista.
4.  Na lista de departamentos exibido, selecione o departamento a ser adicionado à hierarquia.
5.  Salve as alterações. Você receberá uma mensagem informando que uma versão de rascunho da hierarquia foi criada.
6.  Quando você estiver pronto, clique em **Publicar** no designer da hierarquia. Você pode inserir uma data efetiva que indique quando a hierarquia deve ser publicada. Por exemplo, para adicionar um novo departamento no início do próximo ano civil, defina a data efetiva para 1º de janeiro do novo ano civil. As alterações na hierarquia entrarão em vigor nessa data.





