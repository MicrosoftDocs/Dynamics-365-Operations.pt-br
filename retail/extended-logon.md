---
title: "A configuração estendido a funcionalidade de logon do retail do nuvem e o MPOS"
description: "Este wiki aborda as opções para configurar o logon estendido para nuvem POS e Retail Modern POS (MPOS)."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 0dc80784a5c9a7de6009826284cb68f1aee83f70
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-extended-logon-functionality-for-cloud-pos-and-mpos"></a>A configuração estendido a funcionalidade de logon do retail do nuvem e o MPOS

Este wiki aborda as opções para configurar o logon estendido para nuvem POS e Retail Modern POS (MPOS).

<a name="setting-up-extended-logon"></a>Configurando o logon estendido
=========================

Você pode encontrar o de instalação para máscaras de código de barras ** varejo e comércio ** &gt; ** na configuração de canal ** &gt; ** configuração POS ** &gt; ** POS analisa ** &gt; ** ** perfis de funcionalidade. A Guia Rápida **Funções** inclui as seguintes opções relacionadas ao logon estendido.

### <a name="staff-bar-code-logon"></a>Logon de código de barras da equipe

Quando a opção **Logon de código de barras da equipe** é habilitada, os trabalhadores que têm um logon estendido atribuído às suas credenciais de PDV (ponto de venda) podem fazer logon usando um código de barras.

### <a name="staff-bar-code-logon-requires-password"></a>Logon de código de barras da equipe requer senha

Quando a opção **Logon de código de barras da equipe requer senha** é habilitada, o logon de código de barras da equipe seleciona somente o trabalhador atribuído ao logon estendido apresentado. Os trabalhadores ainda devem inserir a senha quando essa opção é habilitada.

### <a name="staff-card-logon"></a>Logon de cartão da equipe

Quando a opção **Logon de cartão da equipe** é habilitada, os trabalhadores que têm um logon estendido atribuído às suas credenciais de PDV (ponto de venda) podem fazer logon usando uma tarja magnética.

### <a name="staff-card-logon-requires-password"></a>Logon de cartão da equipe requer senha

Quando a opção **Logon de cartão da equipe requer senha** é habilitada, o logon de cartão da equipe seleciona somente o trabalhador atribuído ao logon estendido apresentado. Os trabalhadores ainda devem inserir a senha quando essa opção é habilitada.

<a name="assigning-an-extended-logon"></a>Atribuindo um logon estendido
===========================

Por padrão, somente os gerentes podem atribuir o logon estendido aos trabalhadores. Atribuir o logon estendido, acesse ** logon estendido ** no POS. Em busca de um trabalhador inserindo a ID do operador no campo de pesquisa. Selecione o trabalhador e clique em **Atribuir**. Na página seguinte, passe o dedo ou digitalize o logon estendido para atribuir ao trabalhador. Se essa ação for realizada com êxito, o botão **OK **será disponibilizado. Clique em **OK** para salvar o logon estendido desse trabalhador.

<a name="deleting-an-extended-logon"></a>Excluindo um logon estendido
==========================

Para excluir o logon estendido atribuído a um trabalhador, procure o trabalhador usando a operação **Logon estendido**. Selecione o trabalhador e clique em **Cancelar atribuição**. Todas as credenciais de logon estendido associadas a esse trabalhador são removidas.

<a name="extending-extended-logon"></a>Estendendo o logon estendido
========================

O serviço de logon pode ser estendido para oferecer suporte a dispositivos de logon estendido adicionais, como scanners portáteis. Para obter mais informações, consulte a documentação de extensibilidade do PDV.

<a name="using-extended-logon"></a>Usando o logon estendido
====================

Quando o logon estendido for configurado, e um trabalhador receber um código de barras ou uma tarja magnética, o trabalhador precisará apenas passar o dedo ou digitalizar o cartão enquanto a página de logon é exibida. Se for necessário também uma senha para que o logon possa continuar, o trabalhador será solicitado a inserir a senha.


