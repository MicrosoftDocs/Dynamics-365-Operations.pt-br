---
title: "Segurança de instalação para o conteúdo de O power BI de teste da contabilização de custo previsto"
description: "Este tópico explica como você pode propagar a segurança em nível de acesso na contabilização de custo previsto para segurança em nível de linha do power BI Microsoft. Este recurso ajuda a garantia que os usuários verão apenas dados de O power BI que será concedido acesso."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 1e42622e7621c645d7eda3299f78c34c7e41a251
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>Segurança de instalação para o conteúdo de O power BI de teste da contabilização de custo previsto

Este tópico explica como você pode propagar a segurança em nível de acesso na contabilização de custo previsto para segurança em nível de linha do power BI Microsoft. Este recurso ajuda a garantia que os usuários verão apenas dados de O power BI que será concedido acesso.

<a name="overview"></a>Visão Geral
--------

** Análise de contabilização de custo previsto ** o conteúdo de O power BI Microsoft usa a segurança em nível de linha de O power BI para limitar o acesso de usuário. A segurança é baseada em hierarquia organizacional de nível de acesso que é configurada nos parâmetros de contabilidade de custo previsto. Para obter mais informações sobre o teste ** de contabilização de custo previsto põe conteúdo ** de BI, consulte [] conteúdo (contabilização de custo previsto do power BI de teste da contabilização de custo previsto analysis-content-pack.md -).

## <a name="setup"></a>Instalação
De propagar a segurança em nível de acesso de BI, pelo proprietário de conteúdo do power BI deve rastrear essas etapas. ** Observação: ** O usuário que publica ** análise de contabilização de custo previsto ** o conteúdo de O power BI automaticamente se o proprietário. Apenas um proprietário pode configurar a segurança do power BI. Adicionalmente, até que o proprietário adicione outros usuários em PowerBI.com ninguém, a não ser que o proprietário possa ver dados em todos ** análise de contabilização de custo previsto põe conteúdo ** de BI.

1.  Publicar o arquivo de definição para por BI.
2.  Conectar-se PowerBI.com.
3.  Localizar o conjunto de dados para análise ** de contabilização de custo previsto põem ** o conteúdo de BI.
4.  Abra a página de segurança. 

    [![que abre a página (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)]] de segurança (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)

5.  ** Controlador de custo previsto de objeto ** a função é criada anteriormente. Adicione outros membros que são parte do nível de acesso da contabilização de custo previsto hierarquia organizacional. 

    [![que adiciona membros] (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png) (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)]

Os usuários que são adicionados ** controlador de custo previsto da função ** verão apenas os dados que são autorizadas consulte, conforme a definição no nível de acesso da contabilização de custo previsto hierarquia organizacional. ** Observação: ** A segurança em nível de linha se aplica para caixas e relatórios no Microsoft Dynamics 365 para as transações inseridas de O power BI.

## <a name="updating-security"></a>Atualizando a segurança
Se as atualizações são feitas para segurança de nível de acesso na contabilização de custo previsto, além deseja o power BI para refletir as atualizações, você deve atualizar a entidade que a loja para ** análise de contabilização de custo previsto põe conteúdo ** de BI. Depois de concluir a atualização da entidade do 365 para operações, você deve atualizar os artefatos em PowerBI.com. Para obter mais informações sobre como fazer uma atualização da entidade, consulte armazenamento [] entidade (power-bi-integration-entity-store.md#update-entity-store de atualização). O proprietário ** análise de contabilização de custo previsto ** de conteúdo do power BI também deve fazer uma atualização da entidade se os novos usuários são concedidos acesso a hierarquia organizacional. Adicionalmente, o proprietário deve adicionar os novos usuários ** controlador de custo previsto de objeto ** a função em PowerBI.com, para que a segurança em nível de linha seja aplicada para eles.

## <a name="disabling-security"></a>Desabilita a segurança
Estamos supondo que a empresa quer restringir o acesso a dados. Se, por algum motivo, os parâmetros de segurança estão desabilitados quando você executar a contabilização de custo previsto, o proprietário deve adicionar usuários ** contador de custo previsto ** a função do power BI vez. Se você altera a segurança de um estado habilitado em um estado de enfermos, é recomendável remover usuários ** controlador de custo previsto ** de objetos de função. E vice-versa se você registrar permite a segurança. Os usuários podem pertencer as funções. Acesso é comum a união das duas funções. Em caso de ** análise de contabilização de custo previsto põe conteúdo ** de BI, os usuários que tiverem acesso comum ter acesso a dados ilimitado. Se seu meta é aplicar acesso restrito, os usuários serão atribuídos apenas ** custo o controlador de objeto ** a função. Essas atualizações em nível de linha de segurança são efetivadas imediatamente. Os usuários devem afetados atualizar seus browsers.

## <a name="additional-resources"></a>Recursos adicionais
Para saber mais sobre segurança em nível de linha de O power BI [, consulte gerenciar a segurança no modelo em] do power BI (https://powerbi.microsoft.com/en-us/documentation/powerbi-admin-rls/#manage-security-on-your-model).


