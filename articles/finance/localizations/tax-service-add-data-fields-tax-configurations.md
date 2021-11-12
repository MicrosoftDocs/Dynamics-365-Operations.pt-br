---
title: Adicione campos de dados em configurações de imposto
description: Este tópico explica como personalizar as configurações de imposto adicionando campos de dados.
author: Kai-Cloud
ms.date: 10/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 590c2d62995f260ba4277e1031349b0dc43f1417
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2021
ms.locfileid: "7674891"
---
# <a name="add-data-fields-in-tax-configurations"></a>Adicione campos de dados em configurações de imposto

[!include [banner](../includes/banner.md)]

Este tópico explica como personalizar configurações de imposto usando [campos de dados adicionados à integração de imposto](tax-service-add-data-fields-tax-integration-by-extension.md).

## <a name="customize-the-tax-data-model"></a>Personalizar o modelo de dados de imposto

1. No Microsoft Dynamics 365 Finance, acesse **Relatório Eletrônico** > **Configurações de impostos**.
2. Na árvore de configuração, selecione **Modelo de Dados de Cálculo de Imposto**. Em seguida, no Painel de Ações, selecione **Criar configuração**. 

  > [!NOTE] 
  > Se não houver nenhum provedor de configuração disponível, crie um e torne-o ativo para sua configuração de imposto. Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
  
3. Na caixa de diálogo suspensa, selecione **Modelo de documento tributável derivado de Nome: Modelo de Dados de Cálculo de Imposto, Microsoft**, insira um nome para o novo modelo de dados de imposto e selecione **Criar configuração**.
4. Selecione o modelo de dados de imposto recém-criado e, no Painel de ação, selecione **Designer**.
5. Expanda a árvore do modelo de dados, selecione **Linhas** e **Novo**.
6. Na caixa de diálogo **Criar nó**, insira um nome, especifique o tipo de item e selecione **Adicionar**.
7. Adicione as colunas necessárias.
8. No Painel de ações, selecione **Salvar** e **Concluir**.
9. Feche a página e veja a versão completa do modelo de dados de imposto.

## <a name="customize-the-tax-configuration"></a>Personalize a configuração de imposto

1. No Finance, acesse **Relatório eletrônico** > **Configurações de impostos**.
2. Na árvore de configuração, selecione **Configuração de Cálculo de Imposto**. Em seguida, no Painel de Ações, selecione **Criar configuração**.
3. Na caixa de diálogo suspensa, selecione **Configuração de serviço de impostos derivada de Nome: Configuração de Cálculo de Imposto, Microsoft**, insira um nome para a nova configuração de impostos e selecione **Criar configuração**.
4. Selecione a configuração de impostos recém-criada e, no Painel de ação, selecione **Designer**.
5. Na seção **Propriedades**, no campo **Modelo de dados**, selecione o modelo de dados de impostos personalizado criado anteriormente.
6. No campo **Versão do modelo de dados**, selecione a versão completa do modelo de dados de imposto.
7. Selecione **Adicionar** e adicione os cálculos de imposto necessários.
8. No Painel de ações, selecione **Salvar** e **Concluir**.
9. Feche a página e veja a versão completa da configuração de impostos.

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a>Implemente os recursos de imposto na configuração de impostos personalizada

1. Em Regulatory Configuration Service (RCS), acesse **Recursos de globalização** > **Imposto**.
2. Selecione **Adicionar**, insira as informações sobre o novo recurso e selecione **Criar recurso**.
3. Na guia **Versões**, selecione o recurso e selecione **Editar**.
4. Na guia **Geral**, no campo **Versão de configuração**, selecione a configuração de impostos personalizada e a versão.
5. Na caixa de diálogo **Gerenciar colunas**, selecione o cabeçalho e as colunas que deseja incluir na medida no cálculo de impostos personalizado. Em seguida, selecione o botão de seta para a direita e adicione-as à lista **Colunas selecionadas**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
