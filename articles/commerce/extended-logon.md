---
title: Configurar e usar o recurso de logon estendido
description: Este tópico descreve como configurar e usar o recurso de logon estendido do aplicativo de ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: boycez
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: d211ecfe1550f6093e1d35e7c2b37c036b50dd4a
ms.sourcegitcommit: 5aebb181004eb63210503fb566dcda5c55032bee
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491430"
---
# <a name="set-up-and-use-the-extended-logon-capability"></a>Configurar e usar o recurso de logon estendido

[!include [banner](includes/banner.md)]

Este tópico descreve como configurar e usar o recurso de logon estendido do aplicativo de ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.

O Cloud POS (CPOS) e o Modern POS (MPOS) fornecem um recurso de logon estendido que permite que os funcionários da loja de varejo entrem no aplicativo POS digitalizando um código de barras ou passando um cartão usando um leitor de tarja magnética (MSR).

## <a name="set-up-extended-logon"></a>Configurar o logon estendido

Para configurar o logon estendido para terminais de PDV em uma loja de varejo, siga estas etapas.

1. No Commerce headquarters, vá para **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade**. 
2. No painel de navegação esquerdo, selecione o perfil de funcionalidade que está associado à loja de varejo.
3. Na FastTab **Funções**, em **Opções adicionais de autenticação de logon**, defina as seguintes opções como **Sim** ou **Não**, conforme apropriado:

    - **Logon de código de barras da equipe** – defina esta opção como **Sim** se quiser que os trabalhadores efetuem login no PDV, digitalizando um código de barras. 
    - **Logon de código de barras da equipe requer senha** – Defina esta opção como **Sim** se você quiser que seus funcionários digitem uma senha quando entrarem no PDV digitalizando um código de barras.
    - **Logon de cartão da equipe** – defina esta opção como **Sim**, se quiser que seus trabalhadores efetuem-login no PDV, digitalizando um código de barras.
    - **Logon de código de barras da equipe requer senha** – Defina esta opção como **Sim** se você quiser que seus funcionários insiram uma senha quando entrarem no PDV passando um cartão.

O código de barras ou o cartão está associado a credenciais que podem ser atribuídas a um trabalhador. As credenciais devem ter pelo menos seis caracteres. A cadeia que contém os primeiros cinco caracteres deve ser exclusiva e é considerada uma *credential ID* que é usada para pesquisar um trabalhador. Os caracteres restantes são usados para verificação de segurança. Por exemplo, você tem duas placas, uma das quais tem as credenciais 12345DGYDEYTDW e uma delas tem as credenciais 12345EWUTBDAJH. Como essas duas placas têm a mesma ID de credencial, 12345, elas não podem ser atribuídas com êxito a trabalhadores.

## <a name="assign-extended-logon"></a>Atribuir logon estendido

Por padrão, somente os gerentes podem atribuir o logon estendido aos trabalhadores. Para atribuir o logon estendido, acesse **logon estendido** no POS. Em seguida, pesquise um funcionário inserindo o ID de operador do funcionário no campo de busca. Selecione o trabalhador e clique em **Atribuir**. Na página seguinte, passe o dedo ou digitalize o logon estendido para atribuir ao trabalhador. Se essa ação for realizada com êxito, o botão **OK** será disponibilizado. Clique em **OK** para salvar o logon estendido desse trabalhador.

## <a name="delete-extended-logon"></a>Excluir logon estendido

Para excluir o logon estendido atribuído a um trabalhador, procure o trabalhador usando a operação **Logon estendido**. Selecione o trabalhador e clique em **Cancelar atribuição**. Todas as credenciais de logon estendido associadas a esse trabalhador são removidas.

## <a name="use-extended-logon"></a>Usar logon estendido

Depois que o logon estendido é configurado e um código de barras ou tarja magnética é atribuído a um trabalhador, o trabalhador só precisa passar o dedo ou digitalizar seu cartão, enquanto a página de logon do PDV é exibida. Se uma senha também for necessária antes que o logon possa continuar, será solicitado que o funcionário insira sua senha.

## <a name="extend-extended-logon"></a>Estender o logon estendido

A implementação inicial do recurso de logon estendido requer que as credenciais tenham um comprimento mínimo de seis caracteres e que os cinco primeiros caracteres (a ID da credencial) sejam exclusivos. Ele foi originalmente concebido como uma amostra que os desenvolvedores poderiam personalizar para atender aos requisitos de uma implementação específica. (Por exemplo, ele pode ser personalizado para oferecer suporte a mais caracteres ou usar diferentes regras de verificação de segurança.) Para obter informações detalhadas sobre como criar extensões para logon estendido, consulte [Estender a funcionalidade de Logon Estendido para MPOs e PDV em Nuvem](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/12/14/extending-the-extended-logon-functionality-for-mpos-and-cloud-pos/).

O serviço de logon também pode ser estendido para oferecer suporte a dispositivos de logon estendido adicionais, como scanners portáteis. Para obter mais informações, consulte a [documentação de extensibilidade do PDV](dev-itpro/pos-extension/pos-extension-overview.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
