---
title: ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 1 - Preparar modelo de dados)
description: Este artigo descreve como configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída de ER. (Parte 1)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7818b4916de7f3afbead0da39aa471f690d8f5e7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908374"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a>ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 1 - Preparar modelo de dados)

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER. Essas etapas podem ser executadas em qualquer empresa.

Para completar essas etapas, você deve primeiro completar as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".

Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Obter acesso à lista de configurações fornecidas pela Microsoft
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.

    Verifique se o provedor "Litware, Inc." está disponível e marcado como ativo.  

2. Selecione o "Litware, Inc." "Litware, Inc.".
3. Clique em Repositórios.

    Se um repositório do tipo 'Recurso de operações' já existir, ignore as etapas restantes das subtarefa atual.  

4. Clique em Adicionar para abrir a caixa de diálogo suspensa.
5. No campo Tipo de repositório de configuração, insira 'Recursos de operações'.
6. Clique em Criar repositório.
7. Clique em OK.

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a>Obter as configurações do Modelo de fatura de cliente fornecidas pela Microsoft
1. Clique em Mostrar filtros.
2. Aplicar os seguintes filtros: inserir um valor de filtro de "Recursos de operações" no campo "Nome" usando o operador de filtro "começa com"; inserir um valor de filtro de "" no campo Descrição usando o operador de filtro "começa com"
3. Clique em Mostrar filtros.
4. Clique em Abrir.
5. Na árvore, selecione 'Modelo de fatura de cliente'.

    Selecione a configuração do modelo 'Modelo de fatura de cliente' para importá-la.  

6. Clique em Importar.

    Clique em Importar para a versão 1 da configuração selecionada.  

7. Clique em Sim.
8. Feche a página.
9. Feche a página.
10. Clique em Configurações de relatórios.
11. Na árvore, selecione 'Modelo de fatura de cliente'.

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a>Crie o modelo derivado para oferecer suporte ao acesso a arquivos de gerenciamento de documentos.
Você criará nossa própria configuração do Modelo de fatura de cliente derivando-o da configuração fornecida pela Microsoft. Você usará essa configuração para implementar o acesso aos arquivos de gerenciamento de documentos e para disponibilizá-los nos documentos eletrônicos que serão criados com base nesse modelo.  
1. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
2. No campo Novo, digite o nome 'Derivar do Nome: Modelo de fatura de cliente, Microsoft'.
3. No campo Nome, digite 'Modelo de fatura de cliente (personalizada)'.
4. Clique em Criar configuração.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]