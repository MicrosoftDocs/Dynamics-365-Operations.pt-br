---
title: Configurar o SQL Server Reporting Services para implantações locais
description: Este tópico fornece informações sobre como configurar o SQL Server Reporting Services (SSRS) para uma implantação local.
author: PeterRFriis
ms.date: 06/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: peterfriis
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 88e6d5470ff7808a9b6263b6426e19f6ea11493d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755515"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a>Configurar o SQL Server Reporting Services para implantações locais

[!include [banner](../includes/banner.md)]

Siga as etapas deste tópico para configurar o SSRS (SQL Server Reporting Services) para sua implantação do Microsoft Dynamics 365 Finance + Operations (local).

1. Abra o aplicativo Gerenciador de configuração dos serviços de relatório.
2. Deixe o **Nome do servidor** padrão, que deve ser o nome da máquina atual, e a **Instância do servidor de relatório**, **MSSQLSERVER**.
3. Clique em **Conectar**.

    [![Conexão de configuração dos serviços de relatório](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)

4. Clique na guia **Conta de serviços** e verifique se as configurações correspondem ao gráfico a seguir.

    [![Guia de conta de serviços](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)

5. Clique na guia **URL de Serviço Web** e verifique se as configurações correspondem ao gráfico a seguir.

    [![Guia da URL do serviço Web](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)

6. Clique na guia **Banco de dados** e verifique se o **Nome do banco de dados** e as **Configurações credenciais** correspondem ao gráfico a seguir.

    > [!NOTE]
    > Será necessário criar um novo banco de dados. Para fazê-lo, clique em **Alterar Banco de Dados** e depois verifique se o nome do novo banco de dados é: **DynamicsAxReportServer**.

    [![Guia de banco de dados](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)

7. Clique na guia **URL do Portal Web** e verifique se as configurações correspondem ao gráfico a seguir.

    > [!NOTE]
    > Você deve clicar em **Aplicar** para criar e configurar adequadamente o portal.

    [![Guia da URL do Portal Web](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)

    Após a configuração do portal, a guia **Portal da Web** corresponderá ao gráfico a seguir.

    [![guia do portal web](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)

8. Clique na URL dos relatórios para exibir o portal Web SQL Server Reporting Services.
9. Quando estiver no portal, crie uma pasta nomeada **Dynamics**.

    [![pasta do Dynamics](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)

10. No **Gerenciador de configuração dos serviços de relatório**, clique na guia **Configurações de Email** e verifique se as configurações correspondem ao gráfico a seguir.

    [![guia de configurações de email](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)

11. Clique na guia **Conta de execução** e verifique se as configurações correspondem ao gráfico a seguir.

    [![guia da conta de execução](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)

    Não altere as configurações padrão na guia **Chaves de Criptografia**.

    [![guia de chaves de criptografia](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)

12. Clique na guia **Configurações da assinatura** e verifique se as configurações correspondem ao gráfico a seguir.

    [![guia de configurações da assinatura](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)

    Não altere as configurações padrão na guia **Implantação em Expansão**.

    [![guia de implantação em expansão](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)

    Não altere as configurações padrão na guia **Integração do Power BI**.

    [![guia de integração do power bi](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)

13. Clique em **Sair** para fechar o **Gerenciador de configuração dos serviços de relatório**.

    [![fechar o gerenciador de configuração dos serviços de relatório](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
