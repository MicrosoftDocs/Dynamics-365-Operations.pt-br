---
title: Configurar um ambiente para pesquisa de dados mestres
description: Este tópico explica como configurar seu ambiente para usar o recurso de busca de dados mestres de Cálculo de Imposto.
author: kai-cloud
ms.date: 04/21/2021
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
ms.openlocfilehash: 348643d7213b8c053d6a15b4b716a3ce75ba2fa2
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6346365"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Configurar um ambiente para pesquisa de dados mestres

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar seu ambiente para usar o recurso de busca de dados mestres de Cálculo de Imposto.

1. Configure a integração do Power Platform ao Lifecycle Services (LCS). Para obter mais informações, consulte [Integração do Microsoft Power Platform — Visão geral dos suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
2. Configure o Dynamics 365 Finance e o Microsoft Dataverse. Para obter mais informações, consulte [Como obter a solução](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) e [Autenticação e autorização](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
3. Configure as seguintes entidades. Para obter mais informações, consulte [Habilitar entidades virtuais](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).
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
4. Configure o Regulatory Configuration Service (RCS) do Dynamics 365. 
5. Crie uma solicitação de serviço para a Microsoft habilitar a liberação dos seguintes recursos:

      - ERCdsFeature
      - TaxServiceCDSFeature

6. Acesse o espaço de trabalho **Gerenciamento de recursos** e habilite estes recursos:

      - (Versão preliminar) Suporte às fontes de dados do Dataverse para Relatório Eletrônico
      - (Versão preliminar) Suporte à fonte de dados do Serviço de Imposto do Dataverse
      - (Versão preliminar) Recursos de globalização

5. Entre no RCS usando uma conta do administrador de locatário.
6. Acesse **Relatório Eletrônico** > **Aplicativos conectados**. 
7. Selecione **Novo** para adicionar um registro e insira estas informações de campo. 

   - No campo **Nome**, insira um nome.
   - No campo **Tipo**, selecione **Dataverse**.
   - No campo **Aplicativo**, insira sua URL do Dataverse.
   - No campo **Locatário**, insira seu locatário.
   - No campo **URL personalizada**, insira sua URL do Dataverse e inclua "/api/data/v9.1" no final.

8. Selecione **Verificar conexão** e finalize o processo de conexão. 

   [![Botão Verificar conexão.](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

9. Acesse **Relatório Eletrônico** > **Configurações de imposto** e importe configurações de imposto em [Configurações de imposto](https://go.microsoft.com/fwlink/?linkid=2158352).

   [![Página Configurações de imposto, árvore de modelo de dados de imposto.](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

10. Acesse **Mapeamento do modelo de documento tributável** ou **Mapeamento do modelo do Dataverse** se estiver usando uma configuração da Microsoft, e no campo **Aplicativo conectado**, selecione o registro criado na etapa 7.
11. Defina a opção **Padrão do mapeamento de modelo** como **Sim**.

   [![Página Mapeamento do modelo.](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
