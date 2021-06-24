---
title: Regulatory Configuration Service (RCS) - Suspensão do armazenamento do Lifecycle Services (LCS)
description: Este tópico fornece informações sobre a suspensão do armazenamento do Microsoft Dynamics Lifecycle Services (LCS) que foi planejada como parte da distribuição do repositório global do Regulatory Configuration Service (RCS).
author: JaneA07
ms.date: 05/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, LCS storage, LCS storage deprecation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.19
ms.openlocfilehash: abaeb34db1d209fa8e5cc83a98c333f42e91f2d2
ms.sourcegitcommit: 7cda434becd198c1cd405e001289777ae7a24fe1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6127910"
---
# <a name="regulatory-configuration-service-rcs--lifecycle-services-lcs-storage-deprecation"></a>Regulatory Configuration Service (RCS) - Suspensão do armazenamento do Lifecycle Services (LCS)

[!include [banner](../includes/banner.md)]

O uso do Microsoft Dynamics Lifecycle Services (LCS) como repositório de armazenamento para configurações do ER (Relatório Eletrônico) está sendo suspenso. Esta suspensão envolverá as seguintes mudanças:

- As configurações feitas pela Microsoft que são usadas nos aplicativos do Microsoft Dynamics 365 não serão publicadas na Biblioteca de ativos compartilhados no LCS. Em vez disso, elas serão publicadas somente por meio do repositório Global do RCS. No entanto, as configurações para o Dynamics AX 2012 continuarão sendo publicadas na Biblioteca de ativos compartilhados no LCS até que o ciclo de vida de suporte para o AX 2012 termine.
- Será desativada a funcionalidade que permite a você carregar configurações à Biblioteca de ativos de projeto no LCS de aplicativos do Finance and Operations e do RCS. No entanto, você ainda poderá usar o navegador no LCS para carregar configurações na Biblioteca de ativos de projetos. No entanto, você ainda poderá adicionar o navegador ao LCS para que elas sejam incluídas nos pacotes de solução.
- A importação das configurações a partir do LCS continuará disponível e com suporte nos aplicativos no Finance and Operations e no RCS por algum tempo. No entanto, essa funcionalidade será suspensa eventualmente. (A data exata da suspensão será anunciada posteriormente.)

## <a name="deprecation-notice"></a>Aviso de suspensão

A suspensão do uso do LCS como armazenamento foi comunicada no [Recursos suspensos ou preteridos no Dynamics 365 Finance - Aviso de suspensão do LCS](../get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release). A data planejada para a suspensão é 1º de abril, 2022.

## <a name="key-features"></a>Recursos principais

- Você pode usar o RCS para criar e editar configurações. Em seguida, você pode enviar essas configurações diretamente do designer para um aplicativo conectado. Portanto, você pode alterar e testar suas configurações rapidamente.
- O repositório Global é o armazenamento centralizado para todas as configurações do ER.

## <a name="guidance-for-one-time-and-ongoing-actions"></a>Orientação para ações de aplicação única e contínuas

A seção descreve um conjunto de etapas que devem ser concluías uma vez. Isso também descreve as etapas que devem ser concluídas em uma base contínua depois.

### <a name="one-time-action"></a>Ação de aplicação única

Importe todas as configuração necessárias do LCS para o RCS e então publique-as do RCS para o repositório Global. Se você estiver usando bibliotecas de ativos específicas ao projeto para armazenar configurações derivadas no LCS, as etapas a seguir devem ser concluídas enquanto o LCS ainda for acessível.

1. Se uma instância do RCS ainda não estiver disponível, provisione uma. Para obter mais informações, consulte [Visão geral do RCS](rcs-overview.md).
2. Na instância provisionada do RCS, para todo projeto do LCS na Biblioteca de ativos que incluir configurações derivadas do ER, registre o repositório do LCS apropriado.
3. Importe as configurações do ER dos repositórios do LCS para o RCS. Para obter mais informações, consulte [Importar configurações do LCS](../../dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services.md).
4. Se o repositório Global não for obtida automaticamente, registre-o no RCS.
5. Carregue todas as configurações derivadas da instância atual do RCS para o repositório Global. Use o recurso **Pacotes de configuração que permitem ao usuário carregar todas as configurações para o GR em uma única operação** para ajudar com o upload. Para obter mais informações, consulte as [Carregar repositório global do RCS](rcs-global-repo-upload.md).

### <a name="going-forward"></a>A partir de agora

Use os designers de visual do RCS para criar todas as configurações novas. Em seguida, carregue as configurações para o repositório Global para armazenamento.. Para saber mais, consulte [Criar configuração do ER no RCS e carregar para o repositório Global](rcs-global-repo-upload.md).

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="does-this-change-mean-that-lcs-cant-be-used-as-central-storage-for-configurations"></a>Esta mudança significa que o LCS não pode ser usado como armazenamento central para configurações?

Sim. Será suspensa a funcionalidade que permite a você carregar configurações à Biblioteca de ativos de projeto no LCS de aplicativos do Finance and Operations. No entanto, você ainda pode usar o navegador no LCS para carregar configurações na Biblioteca de ativos de projetos conforme necessário.

### <a name="i-thought-that-rcs-was-a-replacement-repository-for-importing-global-template-files-i-didnt-think-that-its-used-to-store-configurations-which-is-correct"></a>Eu pensei que o RCS fosse um repositório substituto para importar arquivos de modelo global. Eu não achei que ele fosse usado para armazenar configurações. Qual opção está correta?

O RCS é um serviço de design para a criação e edição de configurações do ER. O RCS tem seu próprio repositório que é conhecido como o repositório Global. O repositório é usado para armazenar configurações criadas no RCS. Após o LCS como armazenamento for suspenso, o repositório Global será a única fonte para configurações da Microsoft. É necessário realizar uma ação uma única ação para importar todas as configurações que você precisa do LCS para RCS e então publicá-las do RCS para o repositório Global.

### <a name="without-lcs-what-is-the-suggested-way-to-store-configurations-so-that-test-and-production-configurations-can-easily-be-managed-and-transferred"></a>Sem o LCS, qual é a forma sugerida para armazenar configurações, de forma que as configurações "teste" e "produção" possam ser facilmente gerenciadas e transferidas?

O RCS usa o conceito de um *aplicativo conectado*. Um aplicativo conectado forma uma conexão entre o RCS e qualquer instância dos aplicativos do Finance and Operations. Como o RCS pode ser usado para editar configurações, o aplicativo conectado pode ser usado para enviar as configurações diretamente do designer para os ambientes dos aplicativos do Finance and Operations. Portanto, você pode alterar e testar suas configurações rapidamente em vez de precisar passar pelo armazenamento em nível de projeto do LCS.

### <a name="are-there-any-examples-that-show-the-setup-and-management"></a>Há outros exemplos que mostram a configuração e o gerenciamento?

Não há exemplos, mas você pode concluir as etapas mencionadas neste tópico para migrar suas configurações para o repositório Global do RCS.
