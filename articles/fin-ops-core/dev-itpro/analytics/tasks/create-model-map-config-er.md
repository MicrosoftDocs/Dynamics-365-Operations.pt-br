---
title: Gerenciar configurações de mapeamentos de modelo para relatórios eletrônicos (ER)
description: Use este procedimento para criar uma nova configuração de mapeamento de modelo de Relatório eletrônico (ER) e usar funções de ER internas para obter cálculos agregados eficientes.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 23bc3a525be9f65b7e5100114d02f6b79a286fb5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682060"
---
# <a name="create-electronic-reporting-er-model-mapping-configurations"></a>Gerenciar configurações de mapeamentos de modelo para relatórios eletrônicos (ER)

[!include [banner](../../includes/banner.md)]

Use este procedimento para criar uma nova configuração de mapeamento de modelo de Relatório eletrônico (ER) e usar funções de ER internas para obter cálculos agregados eficientes. Neste procedimento, você criará uma configuração para a empresa de exemplo, Litware, Inc. 

Este procedimento é criado para usuários com a função atribuída de Administrador do sistema ou Desenvolvedor de relatório eletrônico.

Estas etapas podem ser concluídas usando qualquer conjunto de dados. Para completar essas etapas, você deve primeiro completar as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
    * Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como Ativo. Se não visualizar este provedor de configuração, conclua as etapas no procedimento "Criar um provedor de configuração e marcá-lo como ativo".  
2. Clique em Configurações de relatórios.
3. Clique em Mostrar filtros.
4. No campo "Nome", digite o valor de filtro "Intrastat" e use o operador de filtro "começa com".
    * Aplique este filtro para localizar a configuração do modelo de dados "Intrastat". Esse modelo pode já existir na árvore de configurações. Se existir, ignore a subtarefa a seguir.   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a>Obter a configuração de modelo intrastat fornecida pela Microsoft
1. Feche a página.
2. Feche a página.
3. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
4. Na lista, localize e selecione o PDV desejado.
    * Selecione o bloco do provedor Microsoft.  
5. Clique em Repositórios.
    * Clique em Repositórios no bloco do provedor Microsoft.  
6. Clique em Mostrar filtros.
7. No campo "Nome do tipo", digite o valor de filtro "recursos" e use o operador de filtro "contém". 
8. Clique em Abrir.
9. Na árvore, selecione 'Modelo intrastat'.
10. Clique em Importar.
11. Clique em Sim.
    * Você importou a configuração de modelo de ER que contém o modelo de dados que usará para explorar como a nova funcionalidade de ER pode ser usada.  
12. Feche a página.
13. Feche a página.
14. Clique em Configurações de relatórios.

## <a name="add-a-new-model-mapping-configuration"></a>Adicionar uma nova configuração de mapeamento de modelo
1. Na árvore, selecione 'Modelo intrastat'.
2. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
3. No campo Novo, digite 'Mapeamento de modelo baseado no modelo de dados intrastat'.
4. No campo Nome, digite 'Mapeamento de amostra de intrastat'.
    * Mapeamento de amostra de intrastat  
5. Clique em Criar configuração.

