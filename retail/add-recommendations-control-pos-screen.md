---
title: "Adicionar um controle de recomendações à página de transação em um dispositivo do PDV"
description: "Este tópico descreve como adicionar um controle de recomendações à tela de transação em um dispositivo do ponto de venda (PDV) usando o designer do layout da tela no Microsoft Dynamics 365 for Operations."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2377b1639a3c95fe6bba4754c4069cc12043e3d3
ms.lasthandoff: 03/31/2017


---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a>Adicionar um controle de recomendações à página de transação em um dispositivo do PDV

[!include[banner](includes/banner.md)]


Este tópico descreve como adicionar um controle de recomendações à tela de transação em um dispositivo do ponto de venda (PDV) usando o designer do layout da tela no Microsoft Dynamics 365 for Operations.

Você pode exibir recomendações de produto no dispositivo do PDV ao usar o Microsoft Dynamics 365 for Operations. *Recomendações* são itens nos quais o cliente pode estar interessado com base no histórico de compras, itens em sua lista de desejos e itens que outros clientes compraram online e em lojas físicas. Para exibir recomendações de produto, é necessário adicionar um controle à tela de transação usando o designer do layout da tela.

## <a name="open-layout-designer"></a>Abrir o designer do layout
1.  Vá para **Varejo e comércio** &gt; **Configuração do canal** &gt; **Configuração do PDV** &gt; **PDV** &gt; **Layouts da tela**.
2.  Use o Filtro Rápido para localizar a tela à qual você deseja adicionar o controle. Por exemplo, filtre o campo **ID do layout da tela** usando um valor de “F2CP16:9M”.
3.  Na lista, localize e selecione o registro desejado. Por exemplo, selecione “Nome: F2CP16:9M ID do layout da tela: F2CP16:9M”.
4.  Clique em **Designer de layout**.
5.  Acompanhe os avisos para iniciar o designer do layout. Quando credenciais forem solicitadas, insira as mesmas credenciais usadas quando o designer do layout foi iniciado na página **Layouts da tela**.
6.  Ao entrar, uma página semelhante à abaixo aparecerá. O layout será diferente dependendo as personalizações feitas para o armazenamento.

[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Escolha uma opção de exibição.
-----------------------

Há duas opções de configurações disponíveis. Escolha a opção que funciona melhor para o armazenamento e siga as demais instruções para concluir a configuração do controle. As duas opções são:
-   As recomendações são sempre visíveis.
-   Uma guia **Recomendações** será exibida na grade à direita da tela.

#### <a name="to-make-recommendations-always-visible"></a>Para tornar as recomendações sempre visíveis

1.  Reduza a altura da área de detalhes das linhas de transação para que ela tenha a mesma altura do painel do cliente à esquerda.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)
2.  No menu à esquerda, arraste e solte o controle de recomendações entre a área de detalhes de linhas de transação e a grade de botões na parte inferior do centro da tela de transação. Redimensione o controle para que ele caiba no espaço.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)
3.  Clique no **X** para salvar e sair do designer do layout.
4.  No Dynamics 365 for Operations, vá para **Varejo e comércio** &gt; **TI de Varejo** &gt; **Agendas de distribuição**.
5.  Na lista, selecione **1090 Registros**.
6.  Clique em **Executar agora**.

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Para adicionar uma guia Recomendações à grade de botões no lado direito da tela

1.  Clique com o botão direito no espaço vazio abaixo da última guia na grade de botões localizada no lado direito da página.
2.  Clique em **Personalizar**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)
3.  Clique em **Nova guia**.
4.  Localize a nova guia que você acabou de adicionar. Talvez você precise rolar para baixo.
5.  No menu suspenso **Conteúdos**, selecione **Produtos recomendados**. [![pic-6](./media/pic-6.png)](./media/pic-6.png)
6.  No campo **Etiqueta**, digite um nome para a guia de recomendações. Por exemplo, digite “Produtos recomendados”.
7.  No campo **Imagem**, selecione a imagem que aparecerá na guia.
8.  Clique em **OK**. A nova guia aparecerá na grade de botões.
9.  Clique no **X** para salvar e sair do designer do layout.
10. No Dynamics 365 for Operations, vá para **Varejo e comércio** &gt; **TI de Varejo** &gt; **Agendas de distribuição**.
11. Na lista, selecione **1090 Registros**.
12. Clique em **Executar agora**.


<a name="see-also"></a>Consulte também
--------

[Visão geral de recomendações de produto personalizado](personalized-product-recommendations.md)




