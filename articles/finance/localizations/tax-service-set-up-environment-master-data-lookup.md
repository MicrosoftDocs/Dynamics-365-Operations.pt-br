---
title: Habilitar pesquisa de dados mestres para configuração de cálculo de imposto
description: Este tópico explica como configurar e habilitar o recurso de pesquisa de dados mestres do cálculo de imposto.
author: kai-cloud
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7640144b1687fc64e55f659d49cdb0817c17294a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686701"
---
# <a name="enable-master-data-lookup-for-tax-calculation-configuration"></a>Habilitar pesquisa de dados mestres para configuração de cálculo de imposto 

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar e habilitar o recurso de pesquisa de dados mestres do cálculo de imposto. Uma lista suspensa está disponível para selecionar valores na configuração do cálculo de imposto para campos como **Entidade legal**, **Conta de fornecedor**, **Código do item** e **Prazo de entrega**. Esses valores são provenientes do ambiente conectado do Microsoft Dynamics 365 Finance usando a fonte de dados do Microsoft Dataverse.

> [!NOTE] 
> A funcionalidade de pesquisa de dados mestres do cálculo de imposto é opcional. É possível ignorar as etapas a seguir se você desabilitar o recurso **Suporte à fonte de dados do Serviço de Imposto do Dataverse** no RCS (Regulatory Configuration Service). No entanto, nesse caso, a lista suspensa não estará disponível na configuração de cálculo de imposto.

1. Configure a integração do Microsoft Power Platform ao Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações, consulte [Integração do Microsoft Power Platform — Visão geral dos suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Depois de concluir esta etapa, o nome de um ambiente do Microsoft Power Platform será exibido na seção **Integração do Power Platform**.
2. Vá para o [centro de administração do Microsoft Power Platform](https://admin.powerplatform.microsoft.com/environments) e selecione o nome do ambiente. A URL do ambiente foi fornecida.
3. Configurar o Dynamics 365 Finance e Dataverse. Para obter mais informações, consulte [Como obter a solução de entidade virtual](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution) e [Autenticação e autorização](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
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
