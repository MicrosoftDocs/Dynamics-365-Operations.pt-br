---
title: Adicionar recomendações à tela de transações
description: Este artigo descreve como adicionar um controle de recomendações à tela de transação em um dispositivo do ponto de venda (PDV) usando o designer de layout de tela no Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4748ade8d6693666b58cbded2123d3449d191509
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862063"
---
# <a name="add-recommendations-to-the-transaction-screen"></a>Adicionar recomendações à tela de transações

[!include [banner](includes/banner.md)]


Este artigo descreve como adicionar um controle de recomendações à tela de transação em um dispositivo do ponto de venda (PDV) usando o designer de layout de tela no Microsoft Dynamics 365 Commerce. Para obter mais informações sobre recomendações de produtos, leia as  [recomendações de produtos na documentação do PDV](product.md).


Você pode exibir as recomendações de produtos no dispositivo do PDV ao usar o Commerce. Para exibir recomendações de produto, é necessário adicionar um controle à tela de transação usando o designer do layout da tela. 

## <a name="open-layout-designer"></a>Abrir o designer do layout

1. Acesse **Varejo e Comércio** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **PDV** &gt; **Layouts da tela**.
2. Use o Filtro Rápido para localizar a tela à qual você deseja adicionar o controle. Por exemplo, filtre o campo **ID do layout da tela** usando um valor de **F2CP16:9M**.
3. Na lista, localize e selecione o registro desejado. Por exemplo, selecione **Nome: F2CP16:9M ID do layout da tela: F2CP16:9M**.
4. Clique em **Designer de layout**.
5. Acompanhe os avisos para iniciar o designer do layout. Quando as credenciais forem solicitadas, insira as mesmas credenciais usadas quando o designer do layout foi iniciado na página **Layouts da tela**.
6. Ao entrar, uma página semelhante à abaixo aparecerá. O layout será diferente dependendo as personalizações feitas para o armazenamento.


    [![Designer de layout.](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)

## <a name="choose-a-display-option"></a>Escolher um opção de exibição

Há duas opções de configurações disponíveis. Escolha a opção que funciona melhor para o armazenamento e siga as demais instruções para concluir a configuração do controle. As duas opções são:

- As recomendações são sempre visíveis.
- Uma guia **Recomendações** será exibida na grade à direita da tela.

### <a name="make-recommendations-always-visible"></a>Torne as recomendações sempre visíveis


1. Reduza a altura da área de detalhes das linhas de transação para que ela tenha a mesma altura do painel do cliente à esquerda.


    [![Altura da área de detalhes das linhas de transação reduzida.](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)

2. No menu à esquerda, arraste e solte o controle de recomendações entre a área de detalhes de linhas de transação e a grade de botões na parte inferior do centro da tela de transação. Redimensione o controle para que ele caiba no espaço.

    [![Controle de recomendações adicionado ao layout.](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)


3. Clique no **X** para salvar e sair do designer do layout.
4. No Commerce, Acesse **Varejo e Comércio** &gt; **TI de Varejo e Comércio** &gt; **Agendas de distribuição**.
5. Na lista, selecione **1090 Registros**.
6. Clique em **Executar agora**.


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Adicione uma guia Recomendações à grade de botões no lado direito da tela

1. Clique com o botão direito no espaço vazio abaixo da última guia na grade de botões localizada no lado direito da página.

2. Clique em **Personalizar**.

    [![Personalização - Caixa de diálogo Controle de guias.](./media/pic-5.png)](./media/pic-5.png)

3. Clique em **Nova guia**.
4. Localize a nova guia que você acabou de adicionar. Talvez você precise rolar para baixo.
5. No menu suspenso **Conteúdos**, selecione **Produtos recomendados**.

    [![Seleção de produtos recomendados no campo Conteúdo.](./media/pic-6.png)](./media/pic-6.png)

6. No campo **Etiqueta**, digite um nome para a guia das recomendações. Por exemplo, digite 'Produtos recomendados'.
7. No campo **Imagem**, selecione a imagem que aparecerá na guia.
8. Clique em **OK**. A nova guia aparecerá na grade de botões.
9. Clique no **X** para salvar e sair do designer do layout.
10. No Commerce, Acesse **Varejo e Comércio** &gt; **TI de Varejo e Comércio** &gt; **Agendas de distribuição**.
11. Na lista, selecione **1090 Registros**.
12. Clique em **Executar agora**.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das recomendações dos produtos](product-recommendations.md)

[Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendações dos produtos](enable-product-recommendations.md)

[Habilitar recomendações personalizadas](personalized-recommendations.md)

[Cancelar recomendações personalizadas](personalization-gdpr.md)

[Habilitar recomendações de "comprar looks semelhantes"](shop-similar-looks.md)

[Adicionar recomendações dos produtos no PDV](product.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Criar recomendações com dados de demonstração](product-recommendations-demo-data.md)

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]