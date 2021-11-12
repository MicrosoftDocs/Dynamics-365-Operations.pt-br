---
title: Configurar um ambiente para pesquisa de dados mestres
description: Este tópico explica como configurar seu ambiente para usar o recurso de busca de dados mestres de Cálculo de Imposto.
author: kai-cloud
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 901f8bcb0220355866952b68e92bc2dd906bb430
ms.sourcegitcommit: 2113678369f47944f8725ca656f461fa159f87f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2021
ms.locfileid: "7700395"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Configurar um ambiente para pesquisa de dados mestres

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar seu ambiente para usar o recurso de busca de dados mestres de Cálculo de Imposto.

1. Configure a integração do Microsoft Power Platform ao Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações, consulte [Integração do Microsoft Power Platform — Visão geral dos suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Depois de concluir esta etapa, o nome de um ambiente do Microsoft Power Platform será exibido na seção **Integração do Power Platform**.
2. Vá para o [centro de administração do Microsoft Power Platform](https://admin.powerplatform.microsoft.com/environments) e selecione o nome do ambiente. A URL do ambiente foi fornecida.
3. Configure o Dynamics 365 Finance e o Dataverse. Para obter mais informações, consulte [Como obter a solução de entidade virtual](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution) e [Autenticação e autorização](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
4. Configure as seguintes entidades. Para obter mais informações, consulte [Habilitar entidades virtuais do Microsoft Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

    - CompanyInfoEntity
    - CurrencyEntity
    - CustCustomerV3Entity
    - DeliveryTermsEntity
    - EcoResProductCategoryEntity
    - EcoResReleasedProductV2Entity
    - LogisticsAddressCityEntity
    - LogisticsAddressCountryRegionTranslationEntity
    - LogisticsAddressStateEntity
    - PurchProcurementChargeCDSEntity
    - SalesChargeCDSEntity
    - TaxGroupEntity
    - TaxItemGroupHeadingEntity
    - VendVendorV2Entity

5. Configure o RCS (Regulatory Configuration Service). Abra o espaço de trabalho **Gerenciamento de recursos** e habilite estes recursos:

    - Suporte às fontes de dados do Dataverse para relatório eletrônico
    - Suporte à fonte de dados do Serviço de Imposto do Dataverse
    - Recursos de globalização

6. Entre no RCS usando uma conta do administrador de locatário.
7. Acesse **Relatório Eletrônico** > **Aplicativos conectados**. 
8. Selecione **Novo** para adicionar um registro e insira estas informações de campo. 

    - No campo **Nome**, insira um nome.
    - No campo **Tipo**, selecione **Dataverse**.
    - No campo **Aplicativo**, insira sua URL do Dataverse.
    - No campo **Locatário**, insira seu locatário.
    - No campo **URL personalizada**, insira sua URL do Dataverse e inclua "/api/data/v9.1" no final.

9. Selecione **Verificar conexão** e finalize o processo de conexão. 

    [![Botão Verificar conexão.](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

10. Acesse **Relatório Eletrônico** > **Configurações de imposto** e importe configurações de imposto em [Configurações de imposto](https://go.microsoft.com/fwlink/?linkid=2158352).

    [![Página Configurações de imposto, árvore de modelo de dados de imposto.](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

11. Acesse **Mapeamento do modelo de documento tributável** ou **Mapeamento do modelo do Dataverse** se estiver usando uma configuração da Microsoft, e no campo **Aplicativo conectado**, selecione o registro criado na etapa 7.
12. Defina a opção **Padrão do mapeamento de modelo** como **Sim**.

    [![Página Mapeamento do modelo.](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
