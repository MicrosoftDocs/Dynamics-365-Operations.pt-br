---
title: Configurar parâmetros compartilhados
description: Você deve configurar parâmetros compartilhados para os registros compartilhados entre empresas, como Registros de posições. Este artigo explica como configurar parâmetros de Recursos humanos entre entidades legais.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 72742c38c3ff25d665bd1a3d0ea54f167dc0693c
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430040"
---
# <a name="configure-shared-parameters"></a>Configurar parâmetros compartilhados

Você deve configurar parâmetros compartilhados para os registros compartilhados entre empresas, como Registros de posições. Este artigo explica como configurar parâmetros de Recursos humanos entre entidades legais.

Alguns tipos de registros, como os registros de posição, são compartilhados entre empresas. Para esses registros, é necessário configurar parâmetros compartilhados. Por exemplo, você pode usar a página **Parâmetros compartilhados de recursos humanos** para configurar parâmetros de recursos humanos entre entidades legais. 

Na página **Parâmetros compartilhados de recursos humanos**, os parâmetros são agrupados em áreas, com base em sua funcionalidade. 

### <a name="previously-released-functionality"></a>Funcionalidade liberada anteriormente
Na guia **Identificação**, selecione os tipos de identificação que representam os números de identificação listados na página. Você deve configurar tipos de identificação para que você possa inserir informações de identificação para trabalhadores. As informações sobre número do seguro social, número de ID nacional, número de ID do estrangeiro e código de ID pessoal são mantidas na página **Tipo de identificação**. Para definir um novo tipo de identificação ou revisar a lista de tipos existentes, clique em **Gerenciamento de pessoal** &gt; **Guia de links** &gt; **Configuração** &gt; **Tipos de identificação**. Você pode inserir um código simples e uma descrição. 

### <a name="if-youre-using-dynamics-365-human-resources"></a>Se você estiver usando o Dynamics 365 Human Resources
Na guia **Identificação**, selecione os tipos de identificação que representam os números de identificação listados na página. Você deve configurar tipos de identificação para que você possa inserir informações de identificação para trabalhadores. As informações sobre número do seguro social, número de ID nacional, número de ID do estrangeiro e código de ID pessoal são mantidas na página **Tipo de identificação**. Para definir um novo tipo de identificação ou revisar a lista de tipos existentes, clique em **Recursos humanos** &gt; **Configuração** &gt; **Tipos de identificação**. Você pode inserir um código simples e uma descrição. 

Na guia **Sequências numéricas**, você pode selecionar as sequências numéricas usadas nos seguintes registros: Número da equipe, Posição, ID da solicitação de usuário, Documento I-9, Candidato, Discussão, ID do Benefício e Ação de pessoal (se esse tipo de registro estiver habilitado). Para manter as referências e os códigos de sequência numérica, use a página de lista **Sequências numéricas**. Para localizar essa página, use o recurso de pesquisa de página. 

Na guia **Posições**, indique se as novas posições estão disponíveis para atribuição por padrão:

-   **Sempre** – Você pode atribuir trabalhadores a novas posições quando estas forem criadas. Quando as posições são criadas, a data e hora **Disponível para a atribuição** na guia **Geral** da página **Posição** são automaticamente definidas para a data e hora de criação.
-   **Nunca** – Você não pode atribuir trabalhadores a novas posições quando estas forem criadas. Se você selecionar essa opção, precisará abrir a página **Posição** para cada nova posição à medida que ela for disponibilizada. Em seguida, na guia **Geral**, insira **Disponível para atribuição** para habilitar a atribuição de trabalhador.
