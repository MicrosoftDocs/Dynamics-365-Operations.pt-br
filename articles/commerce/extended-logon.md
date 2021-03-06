---
title: Configurar a funcionalidade de logon estendido para MPOS e Cloud POS
description: Este tópico aborda as opções para configurar o logon estendido para Cloud POS e Retail Modern POS (MPOS).
author: rubencdelgado
ms.date: 06/20/2017
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
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: f9d8889581e2e11fa5261805c866a6014df57611
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027567"
---
# <a name="set-up-extended-logon-functionality-for-mpos-and-cloud-pos"></a>Configurar a funcionalidade de logon estendido para MPOS e PDV em Nuvem

[!include [banner](includes/banner.md)]

Este tópico aborda as opções para configurar o logon estendido para Cloud POS e Retail Modern POS (MPOS).

## <a name="setting-up-extended-logon"></a>Configurando o logon estendido

Você pode localizar a configuração das máscaras de código de barras em **Retail e Commerce** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Perfis de PDV** &gt; **Perfis de funcionalidade**. A Guia Rápida **Funções** inclui as seguintes opções relacionadas ao logon estendido.

### <a name="staff-bar-code-logon"></a>Logon de código de barras da equipe

Quando a opção **Logon de código de barras da equipe** é habilitada, os trabalhadores que têm um logon estendido atribuído às suas credenciais de PDV (ponto de venda) podem fazer logon usando um código de barras.

### <a name="staff-bar-code-logon-requires-password"></a>Logon de código de barras da equipe requer senha

Quando a opção **Logon de código de barras da equipe requer senha** é habilitada, o logon de código de barras da equipe seleciona somente o trabalhador atribuído ao logon estendido apresentado. Os trabalhadores ainda devem inserir a senha quando essa opção é habilitada.

### <a name="staff-card-logon"></a>Logon de cartão da equipe

Quando a opção **Logon de cartão da equipe** é habilitada, os trabalhadores que têm um logon estendido atribuído às suas credenciais de PDV (ponto de venda) podem fazer logon usando uma tarja magnética.

### <a name="staff-card-logon-requires-password"></a>Logon de cartão da equipe requer senha

Quando a opção **Logon de cartão da equipe requer senha** é habilitada, o logon de cartão da equipe seleciona somente o trabalhador atribuído ao logon estendido apresentado. Os trabalhadores ainda devem inserir a senha quando essa opção é habilitada.

## <a name="assigning-an-extended-logon"></a>Atribuindo um logon estendido

Por padrão, somente os gerentes podem atribuir o logon estendido aos trabalhadores. Para atribuir o logon estendido, acesse **logon estendido** no POS. Em seguida, pesquise um funcionário inserindo o ID de operador do funcionário no campo de busca. Selecione o trabalhador e clique em **Atribuir**. Na página seguinte, passe o dedo ou digitalize o logon estendido para atribuir ao trabalhador. Se essa ação for realizada com êxito, o botão **OK** será disponibilizado. Clique em **OK** para salvar o logon estendido desse trabalhador.

## <a name="deleting-an-extended-logon"></a>Excluindo um logon estendido

Para excluir o logon estendido atribuído a um trabalhador, procure o trabalhador usando a operação **Logon estendido**. Selecione o trabalhador e clique em **Cancelar atribuição**. Todas as credenciais de logon estendido associadas a esse trabalhador são removidas.

## <a name="extending-extended-logon"></a>Estendendo o logon estendido

O serviço de logon pode ser estendido para oferecer suporte a dispositivos de logon estendido adicionais, como scanners portáteis. Para obter mais informações, consulte a documentação de extensibilidade do PDV.

## <a name="using-extended-logon"></a>Usando o logon estendido

Quando um logon estendido e configurado e um funcionário tiver recebido um código de barras ou faixa magnética, o funcionário precisa apenas deslizar ou digitalizar o cartão do funcionário enquanto a página de logon do POS é exibida. Se também for necessário uma senha para continuar o logon, o funcionário é solicitado a inserir a senha do funcionário.


[!INCLUDE[footer-include](../includes/footer-banner.md)]