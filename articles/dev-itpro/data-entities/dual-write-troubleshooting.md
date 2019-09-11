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
ms.openlocfilehash: 5e71729dafd2ad85a01b055363d1c7056b5558b2
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873096"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Guia de solução de problemas para integração de dados

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a>Habilite o rastreamento de plug-in no Common Data Service e inspecione os detalhes de erro do plug-in de gravação dupla

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Se você tiver um problema ou erro durante a sincronização de gravação dupla, siga estas etapas para inspecionar os erros no log de rastreamento.

1. Antes de poder inspecionar os erros, você deve ativar os logs de rastreamento de plug-in. Para obter instruções, consulte a seção "Exibir logs de rastreamento" do [Tutorial: crie e registre um plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).

    Agora você pode inspecionar os erros.

2. Entre no Microsoft Dynamics 365 for Sales.
3. Selecione o botão **Configurações** (o símbolo da engrenagem) e selecione **Configurações Avançadas**.
4. No menu **Configurações**, selecione **Personalização \> Log de Rastreamento de Plug-In**.
5. Selecione **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** como o nome do tipo para mostrar os detalhes do erro.

## <a name="inspect-dual-write-synchronization-errors-in-finance-and-operations"></a>Inspecione erros de sincronização de gravação dupla no Finance and Operations

Siga estas etapas para inspecionar erros durante o teste.

1. Entre Microsoft Dynamics Lifecycle Services (LCS).
2. Abra o projeto do LCS que será submetido a testes de gravação dupla.
3. Selecione **Ambientes hospedados na nuvem**.
4. Faça uma conexão de área de trabalho remota com a máquina virtual (VM) do Dynamics 365 for Finance and Operations usando uma conta local que é mostrada no LCS.
5. Abra o Visualizador de Eventos. 
6. Vá para **Registros de aplicativos e serviços \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacional**. Os erros e os detalhes são exibidos.

## <a name="unlink-one-common-data-service-environment-from-finance-and-operations-and-link-another-environment"></a>Desvincule um ambiente do Common Data Service do Finance and Operations e vincule outro ambiente

Siga as etapas a seguir para atualizar os links.

1. Vá para o ambiente do Finance and Operations.
2. Abra o Gerenciamento de Dados.
3. Selecione **Link para o CDS para aplicativos**.
4. Selecione todos os mapeamentos em execução e depois **Parar**.
5. Selecione todos os mapeamentos e depois **Excluir**.

    > [!NOTE]
    > A opção **Excluir** não estará disponível se o modelo **CustomerV3-Account** estiver selecionado. Limpe a seleção desse modelo, conforme necessário. **CustomerV3-Account** é um modelo provisionado mais antigo e funciona com a solução Prospect to Cash. Como ele é liberado globalmente, aparece em todos os modelos.

6. Selecione **Desvincular ambiente**.
7. Selecione **Sim** para confirmar a operação.
8. Para vincular o novo ambiente, siga as etapas do [guia de instalação](https://aka.ms/dualwrite-docs).
