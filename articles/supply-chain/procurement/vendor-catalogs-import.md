---
title: Importar catálogos do fornecedor
description: Este artigo descreve o processo para importar dados do catálogo do fornecedor.
author: GalynaFedorova
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests, CatVendorCatalogDetails, CatVendorCatalogReleaseApprovedProducts, CatVendorCMRDetails, CatVendorCatalogProductPerCompanyStatus, CatVendorMaintenanceEventLog, CatVendorCatalogReviewTool, CatVendorCatalogFileUpload, CatVendorCatalogMaintenanceRequest, CatVendorCatalogFileInLegalEntity, CatVendorCatalogSchema, CatVendorCatalogFilePreviewPane, CatVendorCatalogImportParameter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gfedorova
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 923715893b9f1c4b87d7bbb67e200f8cb8f92e6b
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015542"
---
# <a name="import-vendor-catalogs"></a>Importar catálogos do fornecedor

[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a>Importação dos catálogos do fornecedor

No Dynamics 365 Supply Chain Management, os profissionais de compra podem criar e manter catálogos para os funcionários da empresa usarem ao solicitar itens e serviços para uso interno. Para criar um catálogo de compras, é possível adicionar itens e serviços que você deseja disponibilizar para os funcionários, importando manualmente os dados do catálogo de produtos ou adicionando manualmente os dados do catálogo de produtos até o produto mestre. 

Você pode carregar os dados do catálogo enviados por um fornecedor do cliente do Microsoft Dynamics 365.

Os dados do produto que um fornecedor envia para você, na forma de um arquivo de solicitação de manutenção de catálogo (CMR), devem estar no formato de arquivo XML. O arquivo CMR deve conter todos os detalhes dos produtos que o fornecedor abastece na sua empresa.

## <a name="import-vendor-catalog-data"></a>Importar dados do catálogo do fornecedor

Para importar os dados do catálogo do fornecedor, conclua as seguintes tarefas:

1. Configure um projeto no espaço de trabalho de Gerenciamento de dados em que você definiu as regras de mapeamento de dados. Selecione **Gerenciamento de dados** e selecione **Configurar funções para projetos de dados**.

2. Configure uma hierarquia de categorias de compras e atribua seus fornecedores às categorias de compras. Se você usar códigos de mercadoria, adicione os códigos de mercadoria às categorias de compras. Para obter informações sobre como configurar uma hierarquia de categorias de compras, consulte [Configurar uma hierarquia de categorias de compras](../procurement/tasks/set-up-procurement-category-hierarchy.md).

3. Configurar o fornecedor para importação de catálogo. Selecione um fornecedor e então selecione **Compras** > **Configurar** > **Configurar o fornecedor para importação de catálogo**.

4. Configure o fluxo de trabalho para importação de catálogo. Crie um modelo do arquivo CMR e compartilhe isso com o fornecedor.

5. Selecione **Compras e Fornecimento** \> **Catálogos** \> **Catálogos do fornecedor** para criar um catálogo do fornecedor. Os arquivos de solicitação de manutenção de catálogo (CMR) recebidos do fornecedor são agrupados nesse catálogo.

6. Carregue o arquivo CMR.

7. Revise, aprove ou rejeite os produtos no catálogo do fornecedor. Os produtos são mapeados automaticamente para as categorias de compras. 

Os produtos aprovados são adicionados ao produto mestre e liberados para as entidades legais selecionadas. Somente os produtos aprovadas podem ser adicionados ao catálogo de compras.

## <a name="generate-a-catalog-import-file-template"></a>Gerar um modelo de arquivo de importação de catálogo

O modelo do arquivo de importação de catálogo é um arquivo XSD usado para criar um arquivo CMR dos produtos de um fornecedor. Você pode usar o arquivo CMR para criar um novo catálogo, substituir um catálogo existente ou modificar um catálogo existente.

1. Selecione **Compras e fornecimento** \> **Catálogos** \> **Catálogos do fornecedor** e clique duas vezes no catálogo com que você deseja trabalhar.

2. Baixe um modelo de importação de catálogo atual (arquivo XSD). Na página **Atualizar catálogo**, no **Painel de ações**, na guia **Catálogos** , no grupo **Informações relacionadas** , clique em **Gerar modelo de catálogo** e selecione **Categoria de compras**.

    - Com a opção **Categoria de compras**, você pode gerar um modelo de catálogo que inclui as categorias de compras nas quais o fornecedor está autorizado a fornecer produtos.

3. Na caixa de diálogo **Salvar como**, selecione o local onde você deseja armazenar o modelo de arquivo de catálogo e salve o arquivo.

Para obter mais informações e ver exemplos, consulte estas postagem de blog: [Catálogos de fornecedor no Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]