---
title: Pesquisa de formato estendido de ER (Relatório eletrônico)
description: Este tópico descreve como uma referência de formato de ER pode ser configurada na pesquisa de formato de ER quando o formato necessário é armazenado no Repositório global.
author: NickSelin
manager: AnnBe
ms.date: 01/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: c72335d7d83934146f827ef0bb568b79a585a7a5
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015111"
---
# <a name="allow-users-to-set-up-an-er-format-reference-inquiring-a-format-from-the-global-repository"></a>Permitir que os usuários configurem uma referência de formato de ER consultando um formato no Repositório global

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Você pode usar a estrutura de ER [(Relatório eletrônico)](general-electronic-reporting.md) a fim de configurar [formatos](general-electronic-reporting.md#FormatComponentOutbound) para documentos de saída de acordo com os requisitos legais de diversos países/regiões. Também é possível usar a estrutura de ER a fim de configurar [formatos](general-electronic-reporting.md#FormatComponentInbound) para analisar documentos de entrada e usar as informações desses documentos para acrescentar ou atualizar dados de aplicativo. Cada um desses formatos pode ser usado na instância do seu Dynamics 365 Finance para manipular documentos comerciais de entrada ou saída como parte de um determinado processo de negócios. 

Normalmente, você deve especificar o formato ER que deve ser usado em um determinado processo de negócios. Para isso, selecione um único formato de ER em um campo de pesquisa configurado como parte dos parâmetros específicos do processo de negócios. Esses campos de pesquisa geralmente são implementados usando a API apropriada da estrutura de ER. Para obter mais informações, consulte [API da estrutura de ER – código para exibir uma pesquisa de mapeamento de formato](er-apis-app73.md#code-to-display-a-format-mapping-lookup).

Por exemplo, ao configurar [parâmetros de comércio exterior](https://docs.microsoft.com/dynamics365/finance/localizations/emea-intrastat#set-up-foreign-trade-parameters), você precisará configurar as referências para formatos de ER individuais que serão usados para gerar a declaração Intrastat e o relatório de controle de declaração Intrastat. As capturas de tela abaixo mostram a aparência do campo de pesquisa de formatos de ER na página **Parâmetros de comércio exterior**.

Se a instância atual de Finance não contiver formatos de ER relacionados ao processo de negócios Intrastat, esse campo de pesquisa ficará vazio.

[![Página Parâmetros de comércio exterior](./media/ER-ExtLookup-Lookup1.gif)](./media/ER-ExtLookup-Lookup1.gif)

Se a instância atual de Finance contiver formatos de ER relacionados ao processo de negócios Intrastat, esse campo de pesquisa oferecerá os formatos de ER.

[![Página Parâmetros de comércio exterior](./media/ER-ExtLookup-Lookup2.png)](./media/ER-ExtLookup-Lookup2.png)

Essa pesquisa oferece somente os formatos de ER que já foram importados para a instância atual do Finance. Para [importar](./tasks/er-import-configuration-lifecycle-services.md) soluções ER para a atual instância de Finance, você precisa ter permissões para executar a função apropriada da estrutura de ER que dá suporte ao [ciclo de vida](general-electronic-reporting-manage-configuration-lifecycle.md) das soluções ER que contêm os formatos de ER.

A partir do Finance versão 10.0.9 (lançamento de abril de 2020), a interface de usuário da pesquisa de formato de ER que é implementada usando a API da estrutura de ER, foi estendida. Você ainda pode selecionar os formatos de ER existentes, que estão na FastTab **Selecionar configuração do formato**. Além disso, a pesquisa estendida oferece a nova opção de procurar o GR (Repositório global) para localizar formatos de ER específicos. Todos os formatos de ER do GR são oferecidos na FastTab **Importar do Repositório global**.

[![Página Parâmetros de comércio exterior](./media/ER-ExtLookup-Lookup3.png)](./media/ER-ExtLookup-Lookup3.png)

Semelhante à FastTab **Selecionar configuração do formato**, a FastTab **Importar do Repositório global** mostra apenas os formatos de ER que são aplicáveis ao processo de negócios para os quais um formato de ER é selecionado nesse campo de pesquisa. Neste exemplo, a geração da declaração Intrastat. O formato de ER é aplicável para a empresa à qual o usuário está conectado no momento, dependendo do contexto de país da empresa.

Quando você seleciona um formato de ER na FastTab **Importar do Repositório global**, a [configuração](general-electronic-reporting.md#Configuration) do formato de ER selecionado é importada do GR para a atual instância de Finance.

[![Página Parâmetros de comércio exterior](./media/ER-ExtLookup-FormatImport.png)](./media/ER-ExtLookup-FormatImport.png)

Assim, se a importação for concluída com êxito, a referência para o formato de ER importada será armazenada nesse campo de pesquisa. Observe que ao acessar o GR pela primeira vez, você precisará seguir o link fornecido para inscrever-se no RCS [(Regulatory Configuration Service)](https://aka.ms/rcs) que é usado para gerenciar o acesso ao armazenamento do GR.

[![Página Parâmetros de comércio exterior](./media/ER-ExtLookup-RepoSignUp.png)](./media/ER-ExtLookup-RepoSignUp.png)

Por padrão, a FastTab **Importar do Repositório global** apresenta a lista de formatos de ER do armazenamento temporário que é criada automaticamente com base no conteúdo do GR para melhorias de desempenho. Isso ocorre quando a FastTab **Importar do Repositório global** é aberta pela primeira vez, o que pode demorar alguns segundos.

Se você não visualizar o formato obrigatório de ER na FastTab **Importar do Repositório global**, mas tiver certeza de que esse formato de ER está armazenado no GR, selecione a opção **Sincronizar**. Isso atualizará o armazenamento temporário e o sincronizará com o conteúdo atual do GR.

## <a name="feature-activation"></a>Ativação de recurso

A disponibilidade dessa funcionalidade é controlada pelo recurso **Pesquisa estendida das configurações de formato de ER que permite consultar o Repositório global** no **Gerenciamento de recursos**. Esse recurso é habilitado por padrão.

[![Página Gerenciamento de recursos](./media/ER-ExtLookup-FeatureMngt.png)](./media/ER-ExtLookup-FeatureMngt.png)

## <a name="security-considerations"></a>Considerações de segurança

O privilégio **Manter repositórios de configuração** (**ERMaintainSolutionRepositories**) controla o acesso ao GR para um usuário que abre a pesquisa de formato de ER com a FastTab **Importar do Repositório global**. Para permitir que os usuários acessem o conteúdo do GR a partir das pesquisas de formato de ER, é preciso alterar as configurações de segurança concedendo o privilégio **ERMaintainSolutionRepositories** aos usuários, diretamente ou usando funções e direitos já atribuídos.

A captura de tela a seguir mostra como esse privilégio pode ser concedido aos usuários atribuídos à função **Contador**. Essa função permite que os usuários configurem parâmetros de comércio exterior e referências para os formatos de ER nos campos **Mapeamento de formato de arquivo** e **Mapeamento de formato de relatório** na página **Parâmetros de comércio exterior**.

[![Página Configuração de segurança](./media/ER-ExtLookup-SecuritySetting.png)](./media/ER-ExtLookup-SecuritySetting.png)

## <a name="limitations"></a>Limitações

Atualmente, o acesso ao GR na pesquisa de formato de ER só é permitido para a seleção de formatos de ER que são usados para gerar documentos de saída.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="why-cant-i-access-the-global-repository-from-the-er-format-lookup"></a>Por que não consigo acessar o Repositório global a partir da pesquisa de formato de ER?

Se você habilitou o recurso **Pesquisa estendida das configurações de formato de ER que permite consultar o Repositório global** na página **Gerenciamento de recursos**, mas os usuários não conseguem ver os formatos de ER na FastTab **Importar do Repositório global** e a opção **Sincronizar** está visível mas desabilitada, verifique se o privilégio **Manter repositórios de configuração** (**ERMaintainSolutionRepositories**) foi concedido ao usuário. Entre em contato com o administrador de sistema para receber esse privilégio.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)
- [API da estrutura de ER (Relatório eletrônico)](er-apis-app73.md)
- [Gerenciar o ciclo de vida das configurações de ER (Relatório eletrônico)](general-electronic-reporting-manage-configuration-lifecycle.md)
