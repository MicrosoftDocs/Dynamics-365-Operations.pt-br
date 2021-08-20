---
title: Configurar um depósito usando um modelo de configuração de depósito
description: Este tópico explica como configurar um depósito usando um modelo de configuração de depósito.
author: perlynne
ms.date: 11/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportEnhanced, DMFDefinitionGroupTemplate, DMFEntityTemplateDefinitionLoadDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: adb14507ad26879ee4811c6eb984ce3888b1913a0e6f0664a99079ba49f1a4c5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751904"
---
# <a name="set-up-a-warehouse-by-using-a-warehouse-configuration-template"></a>Configurar um depósito usando um modelo de configuração de depósito

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar um depósito usando um modelo de configuração de depósito. Há vários modelos predefinidos de configuração que você pode usar. Para obter informações sobre como usar esses modelos, consulte [Modelos de dados de configuração](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md).

## <a name="scenarios-where-configuration-templates-can-be-helpful"></a>Cenários onde os modelos de configuração podem ser úteis

Os modelos de configuração podem ser úteis em vários cenários. Eis alguns exemplos:

- Você concluiu e testou uma definição de configuração em um ambiente de teste e agora quer copiar a configuração para um ambiente de produção.
- Você quer implementar a configuração do depósito para várias entidades legais ou criar um novo depósito na mesma entidade legal.
- Você quer preparar rapidamente uma demonstração de funcionalidade de depósito.
- Você quer que os itens e depósitos existentes usem a funcionalidade no Gerenciamento de depósito, em vez da funcionalidade no gerenciamento de estoque.

Esse tópico concentra-se no primeiro desses cenários. Ele mostra como é possível usar um modelo de configuração para copiar uma definição de configuração de um ambiente de teste para um ambiente de produção.

## <a name="copy-a-configuration-setup-from-a-test-environment-to-a-production-environment"></a>Copiar uma definição de configuração de um ambiente de teste para um ambiente de produção

Para esse cenário, a definição de configuração para um depósito e alguns processos de transação já existem em um ambiente de teste. Agora você deseja copiar a definição de configuração do depósito do ambiente de teste para um ambiente de produção.

> [!NOTE]
> É importante que você inclua outros dados relacionados à configuração ao copiar uma definição de configuração. Por exemplo, você quer configurar produtos copiando a definição de um ambiente de teste. Porém, você não pode configurar uma localização fixa de separação para um produto antes de o produto ser criado. Embora os modelos de configuração individuais não ofereçam suporte a esse tipo de dependência, há modelos de dados padrão que oferecem. Você pode incluir facilmente esses modelos de dados padrão em um processo de configuração.

### <a name="export-a-default-warehouse-template"></a>Exportar um modelo padrão do depósito 

1. Abra o espaço de trabalho **Gerenciamento de dados**.

    > [!NOTE]
    > Se estiver usando esse espaço de trabalho pela primeira vez, você deve carregar todas as entidades de dados antes de você prosseguir.

2. Selecione o bloco **Modelos** e, em seguida, selecione **Carregar modelos padrão** para carregar os modelos padrão.

    > [!NOTE]
    > **Carregar modelos padrão** está disponível apenas na exibição **Avançada**. Selecione **Parâmetros de estrutura** e, depois, no campo **Padrões de exibição**, selecione **Exibição avançada**.

3. Depois que os modelos padrão forem carregados, você pode alterá-los, de forma que eles atendam seus requisitos de negócios.

    > [!NOTE]
    > Para carregar modelos padrão e importar modelos, você deve ter o acesso de administrador do sistema. Esse requisito ajuda a garantir de que todas as entidades serão carregadas corretamente no modelo.

4. Certifique-se de que está na entidade legal da qual você deseja exportar os dados específicos da empresa.
5. No espaço de trabalho, selecione **Exportar**.
6. Criar um novo projeto de exportação.
7. Selecione **+ Adicionar modelo** e localize o modelo de depósito padrão **400 - WMS**. Esse modelo adiciona as entidades de dados à configuração de depósito.

    > [!NOTE]
    > Se os dados que você está exportando tiverem que ser filtrados (por exemplo, você quiser exportar somente dados relacionados a um depósito específico), você deve avaliar cada entidade de dados e adicionar a filtragem por meio de uma consulta. Se preferir, você pode exportar os dados e excluir os registros que não são necessários nos arquivos de destino.

8. Selecione **Exportar**. Os dados relacionados a todas as entidades de dados no projeto serão exportados.

Podem baixar um arquivo zip para o pacote de dados. Este arquivo contém todos os dados no formato selecionado (por exemplo, formato Excel). Como foi mencionado, alguns registros nos arquivos do pacote de dados precisam ser atualizados antes para que possa importá-los no ambiente de produção. Se você atualizar um registro, certifique-se de que não alterou o nome do arquivo.

### <a name="import-a-warehouse-configuration-setup"></a>Importar uma definição de configuração do depósito

1. No ambiente de destino, verifique se você está na empresa na qual deseja importar os dados de depósito.

    > [!NOTE]
    > Antes de fazer a importação, é preciso identificar todas as dependências de dados. Por exemplo, o modelo **Gerenciamento de depósito** inclui uma entidade de dados que é chamada **Códigos de disposição de depósito**. Esta entidade contém dados relacionados à página de configuração **Códigos de disposição** (**Gerenciamento de depósito** > **Configuração** > **Dispositivo móvel** > **Códigos de disposição**). Se uma configuração existente já trata o processo de devoluções para ordens de venda, o campo **Código de disposição de devolução** conterá um valor. O código de disposição neste campo está relacionado à entidade de dados **Código de disposição**, que faz parte do modelo **Vendas e marketing**. Se os dados da entidade de dados **Código de disposição** não forem importados antes de os dados do campo **Códigos de disposição de depósito**, haverá falha na importação.

2. No espaço de trabalho **Gerenciamento de dados**, selecione **Importar**.
3. Criar um novo projeto de importação.
4. Selecione **+ Adicionar arquivo** e carregue o arquivo zip para o pacote de dados.
5. Selecione **Importar**. Na exibição **Avançada**, você pode usar a opção **Filtro** rapidamente obter uma visão geral de problemas que podem ocorrer durante a importação.

O log **Exibir execução** fornece informações detalhadas sobre cada entidade de dados que é importada. Você pode usar a exibição de preparação de dados para obter dados de destino rapidamente. Assim, você pode ver os dados importados nas páginas relacionadas no aplicativo. Ao usar os modelos de dados padrão, a sequência de importação de cada entidade de dados em forma predefinida, ajuda a garantir que os dados dependentes são importados primeiro. Se as entidades de dados personalizados fizerem parte do projeto, você deve garantir que a sequência correta foi definida. Para obter mais informações, consulte [Modelos de dados de configuração](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md).

Para saber mais sobre como usar o modelo de depósito para copiar a configuração de um depósito de uma empresa para uma nova empresa na mesma a instância, assista a este vídeo de 3 minutos de duração no YouTube sobre [como usar o modelo de depósito para copiar a configuração no Finance and Operations](https://www.youtube.com/watch?v=K2WIfFlqJYs).

## <a name="related-topic"></a>Tópico relacionado

[Modelos de dados de configuração](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]