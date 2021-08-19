---
title: Configurar parâmetros compartilhados
description: Você deve configurar parâmetros compartilhados para os registros compartilhados entre empresas, como Registros de posições. Este artigo explica como configurar parâmetros de Recursos humanos entre entidades legais.
author: andreabichsel
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 66f57c9613ba04ebb3748699105469586c27d66131c062d1af286b24199c4be7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723638"
---
# <a name="configure-shared-parameters"></a>Configurar parâmetros compartilhados

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Você deve configurar parâmetros compartilhados para os registros compartilhados entre empresas, como Registros de posições. Este artigo explica como configurar parâmetros de Recursos humanos entre entidades legais.

Alguns tipos de registros, como os registros de posição, são compartilhados entre empresas. Para esses registros, é necessário configurar parâmetros compartilhados. Por exemplo, você pode usar a página **Parâmetros compartilhados de recursos humanos** para configurar parâmetros de recursos humanos entre entidades legais. 

Na página **Parâmetros compartilhados de recursos humanos**, os parâmetros são agrupados em áreas, com base em sua funcionalidade. 

### <a name="settings"></a>Configurações
Na guia **Identificação**, selecione os tipos de identificação que representam os números de identificação listados na página. Você deve configurar tipos de identificação para que você possa inserir informações de identificação para trabalhadores. As informações sobre número do seguro social, número de ID nacional, número de ID do estrangeiro e código de ID pessoal são mantidas na página **Tipo de identificação**. Para definir um novo tipo de identificação ou revisar a lista de tipos existentes, clique em **Gerenciamento de pessoal** &gt; **Guia de links** &gt; **Configuração** &gt; **Tipos de identificação**. Você pode inserir um código simples e uma descrição. 

Na guia **Sequências numéricas**, você pode selecionar as sequências numéricas usadas nos seguintes registros: Número da equipe, Posição, ID da solicitação de usuário, Documento I-9, Candidato, Discussão, ID do Benefício e Ação de pessoal (se esse tipo de registro estiver habilitado). Para manter as referências e os códigos de sequência numérica, use a página de lista **Sequências numéricas**. Para localizar essa página, use o recurso de pesquisa de página. 

Na guia **Posições**, indique se as novas posições estão disponíveis para atribuição por padrão:

- **Sempre** – Você pode atribuir trabalhadores a novas posições quando estas forem criadas. Quando as posições são criadas, a data e hora **Disponível para a atribuição** na guia **Geral** da página **Posição** são automaticamente definidas para a data e hora de criação.
- **Nunca** – Você não pode atribuir trabalhadores a novas posições quando estas forem criadas. Se você selecionar esta opção, deverá abrir a página **Cargo** para cada novo cargo quando ele for disponibilizado. Em seguida, na guia **Geral**, insira a data **Disponível para atribuição** a fim de habilitar a atribuição de trabalhador.

Na guia **Acesso avançado**, você pode restringir o acesso a algumas informações ou links:

- **Restringir o acesso às informações do trabalhador** – Ative esse recurso se os usuários só conseguirem exibir informações do funcionário para as entidades legais às quais têm acesso e para os funcionários que têm emprego nessas entidades legais.

    Após a ativação deste recurso, você deve seguir estas etapas para definir as permissões apropriadas para cada usuário cujo modo de exibição deve ser restrito:

    1. Na página **Usuários**, selecione um usuário.
    1. Selecione uma função para o usuário. A opção **Atribuir organizações** é disponibilizada.
    1. Selecione **Atribuir organizações**.
    1. Na nova página, selecione **Conceder acesso a organizações específicas individualmente** e selecione as organizações às quais o usuário deve ter acesso.
    1. Repita as etapas 2 a 4 para cada função do usuário, incluindo a função de usuário do sistema.

    > [!NOTE]
    > As empresas às quais um usuário tem acesso devem coincidir com todas as funções do usuário.

- **Habilitar exibição de remuneração intercompanhia** – A remuneração para funcionários é atribuída por entidade legal de emprego. Às vezes, um funcionário pode ser empregado em várias entidades legais ao mesmo tempo. Quando este recurso está ativado, a remuneração de cada entidade legal aparecerá no Autoatendimento do funcionário e no Autoatendimento do gerente sem exigir que você altere as entidades legais. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
