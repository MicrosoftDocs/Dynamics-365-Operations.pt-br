---
title: Guia de solução de problemas para integração de dados
description: Este tópico fornece informações de solução de problemas para integração de dados entre o Microsoft Dynamics 365 for Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797266"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Guia de solução de problemas para integração de dados

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a>Habilite o Rastreamento de Plug-in no Common Data Service e verifique os detalhes de erro do Plug-in de gravação dupla

Se estiver enfrentando um problema ou erro de sincronização de gravação dupla, você poderá inspecionar os erros no log de rastreamento:

1. Para poder inspecionar os erros, você deve habilitar o rastreamento de plug-in usando as instruções em [Registrar plug-in](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) para habilitar o rastreamento de plug-in. Agora você pode inspecionar os erros.
2. Faça logon no Dynamics 365 for Sales.
3. Clique no ícone Configurações (uma engrenagem) e selecione **Configurações Avançadas**.
4. No menu **Configurações**, escolha **Personalização > Log de Rastreamento de Plug-In**.
5. Clique no nome do tipo **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** para exibir os detalhes do erro.

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a>Verifique erros de sincronização de gravação dupla no Finance and Operations

Você pode verificar os erros durante os testes seguindo estas etapas:

+ Faça logon no Lifecycle Services (LCS).
+ Abra o projeto LCS escolhido para realizar testes de gravação dupla.
+ Vá para Ambientes Hospedados na Nuvem
+ Área de trabalho remota para VM do Finance and Operations usando a conta local que é exibida no LCS.
+ Abra o visualizador de eventos. 
+ Navegue para **Logs de Aplicações e Serviços > Microsoft > Dynamics > AX-DualWriteSync > Operacional**. Os erros e os detalhes são exibidos.

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a>Como desvincular e vincular outro ambiente do Common Data Service a partir do Finance and Operations

Você pode atualizar links executando estas etapas:

+ Navegue para o ambiente do Finance and Operations.
+ Abra o Gerenciamento de Dados.
+ Clique em **Link para o CDS para aplicativos**.
+ Selecione todos os mapeamentos em execução e clique em **Parar**. 
+ Selecione todos os mapeamentos e clique em **Excluir**.

    > [!NOTE]
    > A opção **Excluir** não aparecerá se o modelo **CustomerV3-Account** for selecionado. Desmarque-o se necessário. **CustomerV3-Account** é um modelo provisionado mais antigo e funciona com a solução Prospect to Cash. Como ele é liberado globalmente, aparece em todos os modelos.

+ Clique em **Desvincular ambiente**.
+ Clique em **Sim** para confirmação.
+ Para vincular o novo ambiente, siga as etapas do [guia de instalação](https://aka.ms/dualwrite-docs).

