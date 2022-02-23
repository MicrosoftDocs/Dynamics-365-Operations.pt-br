---
title: 'ER Configurar o formato para contagem e soma (Parte 1: Criar formato)'
description: As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1742582057cc912d8e6f90eb14e9e4cdcd193608
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684706"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a>ER Configurar o formato para contagem e soma (Parte 1: Criar formato)

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída. Essas etapas podem ser executadas em qualquer empresa.

Para completar essas etapas, você deve primeiro completar as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".

Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Obter acesso à lista de configurações fornecidas pela Microsoft
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
    * Verifique se o provedor "Litware, Inc." está disponível e marcado como ativo.  
2. Selecione o provedor "Litware, Inc.".
3. Clique em Repositórios.
    * Se um repositório do tipo "Recursos de operações" já existir, ignore as etapas restantes da subtarefa atual.  
4. Clique em Adicionar para abrir a caixa de diálogo suspensa.
5. No campo Tipo de repositório de configuração, insira 'Recursos de operações'.
6. Clique em Criar repositório.
7. Clique em OK.

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a>Obter as configurações do intrastat fornecidas pela Microsoft
1. Clique em Abrir.
2. Na árvore, selecione 'Modelo intrastat\Intrastat (DE)'.
3. Clique em Importar.
    * Clique em Importar para a versão 1.1 da configuração selecionada.  
4. Clique em Sim.
5. Feche a página.
6. Feche a página.
7. Clique em Configurações de relatórios.
8. Na árvore, expanda 'Modelo intrastat'.
9. Na árvore, selecione 'Modelo intrastat\Intrastat (DE)'.

