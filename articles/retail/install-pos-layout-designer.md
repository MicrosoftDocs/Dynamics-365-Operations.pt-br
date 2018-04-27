---
title: Instalar o designer do layout de PDV
description: "Você pode usar o designer de um clique para criar diferentes layouts de Retail Modern POS (MPOS) e PDV em Nuvem, no modo Paisagem ou modo Retrato, para lojas, registradoras, caixas e gerentes."
author: athinesh99
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 219684
ms.assetid: 2e2c4eea-c6e2-4912-9832-a6b22416e39f
ms.search.region: Global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8fdebf692bd3cd8500274cc73ca5b0591dba4140
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="install-the-retail-pos-layout-designer"></a>Instalar o designer do layout de PDV

[!INCLUDE [banner](includes/banner.md)]

Você pode usar o designer de um clique para criar diferentes layouts de Retail Modern POS (MPOS) e PDV em Nuvem, no modo Paisagem ou modo Retrato, para lojas, registradoras, caixas e gerentes.

O design gráfico da interface do MPOS ou PDV em Nuvem é controlado pelo layout da gaveta do caixa. O layout controla a posição de vários objetos. Exemplos incluem o layout total, o layout da grade de itens, o layout do cliente, o layout de pagamento e o layout de vários botões de menu. Os layouts também incluem a aparência geral da interface de vendas que é apresentada aos trabalhadores.

## <a name="install-the-one-click-designer"></a>Instalar o designer de um clique
1.  No Microsoft Dynamics 365 for Retail, use o menu na parte superior esquerda para navegar para **Varejo** **e comércio** &gt; **Configuração de canal** &gt; **Configuração de PDV** &gt; **PDV** &gt; **Layouts de tela**.
2.  Selecione qualquer layout que tenha um tipo de aplicativo **Modern POS para Windows** ou **PDV em nuvem**, em seguida clique em **Designer do layout**.
3.  Na barra de notificação exibida na parte inferior da janela do Internet Explorer, clique em **Abrir** para instalar o designer de um clique. (A barra de notificação pode aparecer em um local diferente em outros navegadores).
4.  Na caixa de mensagem que aparece **Execução de Aplicativo - Aviso de Segurança**, clique em **Executar** para instalar o host designer varejista. O indicador de progresso mostra o progresso do processo de instalação.
5.  Depois que a instalação for concluída, na página **Entrar**, insira seu nome de usuário e senha do Microsoft Dynamics 365 for Retail, e clique em **Entrar** para iniciar o designer.
6.  Depois que suas credenciais forem validadas e o designer for iniciado, você poderá criar o seu próprio layout ou modificar o formato existente. [![Layout no designer de um clique](./media/screenlayoutdesign_mposdownload-1024x664.png)](./media/screenlayoutdesign_mposdownload.png)

## <a name="troubleshoot-the-installation-of-the-layout-designer"></a>Solucionar problemas da instalação do Designer de layout
-   Quando você clica em **Designer**, o prompt para baixar (ou executar) o instalador não aparece, ou as configurações de segurança atuais não permitem que você baixe o arquivo. **Soluções:**
    -   Internet Explorer, verifique se o bloqueador de pop-ups está desabilitado para esse site. Clique em **Configurações** &gt; **Opções** &gt; **Privacidade** &gt; **Localizar bloqueador de pop-up** e altere a configuração se necessário.
    -   No Internet Explorer, adicione a URL do Dynamics 365 for Retail aos seus sites confiáveis. Clique em **Configurações** &gt; **Opções** &gt; **Segurança** &gt; **Sites confiáveis** &gt; **Sites** &gt; **Adicionar**.
-   O programa não é iniciado, e você é orientado a entrar em contato com o fornecedor. **Solução:** No Internet Explorer, adicione a URL do Dynamics 365 for Retail aos seus sites confiáveis. Clique em **Configurações** &gt; **Opções** &gt; **Segurança** &gt; **Sites confiáveis** &gt; **Sites** &gt; **Adicionar**.

**Problema conhecido:** O designer não funciona corretamente em navegadores Google Chrome e Mozilla Firefox. Estamos trabalhando para solucionar o problema.

<a name="see-also"></a>Consulte também
--------

[Configurar, baixar, instalar e ativar o Retail Modern POS](retail-modern-pos-device-activation.md)




