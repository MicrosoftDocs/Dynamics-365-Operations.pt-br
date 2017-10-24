--- 
title: Gerenciar unidade de medida
description: "Este procedimento mostra como definir uma unidade de medida, fornecer traduções para a unidade e para suas descrições, e definir regras de conversão para unidades relacionadas."
author: sorenva
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6bb7a5133e9412f4ed6fb74f0d3ee595c07a0c4b
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="manage-unit-of-measure"></a>Gerenciar unidade de medida

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como definir uma unidade de medida, fornecer traduções para a unidade e para suas descrições, e definir regras de conversão para unidades relacionadas. Você pode explorar esse procedimento usando os dados demonstrativos, ou usando seus próprios dados.

1. Vá para Manutenção de produto lançado.
2. Clique em Unidades.

## <a name="create-a-unit-of-measure"></a>Criar uma unidade de medida
1. Clique em Novo.
2. No campo Unidade, digite um valor.
    * Insira o ID ou símbolo a ser usado para se referir à unidade de medida.  
3. No campo Descrição, digite um valor.
    * Insira um nome descritivo para a unidade de medida no idioma do sistema.  
4. No campo Classe de unidade, selecione uma opção.
    * A classe de unidade define a qual agrupamento lógico, como área, massa ou quantidade, a unidade de medida pertence.  
5. No campo Precisão decimal, insira um número.
    * Especifique o número de decimais ao qual a unidade de medida convertida deve ser arredondada quando um cálculo é concluído para a unidade de medida.  
6. Clique em Salvar.

## <a name="define-unit-translations"></a>Definir traduções de unidades
1. Clique em Textos de unidade.
2. Clique em Novo.
    * Use texto de unidade para criar uma tradução de ID ou símbolo que representa a unidade de medida para o uso em documentos externos nos idiomas específicos do cliente ou fornecedor.  
3. No campo Idioma, insira ou selecione um valor.
4. No campo Texto, digite um valor.
5. Clique em Salvar.
6. Feche a página.
7. Clique em Descrições da unidade traduzida.
8. Clique em Novo.
    * Defina descrições específicas para um idioma para a unidade de medida.  
9. No campo Idioma, insira ou selecione um valor.
10. No campo Descrição, digite um valor.
11. Clique em Salvar.
12. Feche a página.

## <a name="define-unit-conversion-rules"></a>Definir regras de conversão de unidades
1. Clique em Conversões de unidade.
    * Defina regras de conversão da unidade de medida de e para outras unidades de medida da classe de unidades selecionada.  
2. Clique em Novo para abrir a caixa de diálogo suspensa.
3. No campo Fator, insira um número.
    * Fator de conversão entre De unidade e Para unidade. Por exemplo, o fator de conversão de centímetro para metro é 100 porque existem 100 centímetros em um metro.  
4. No campo Para unidade, insira ou selecione um valor.
5. No campo Arredondamento, selecione uma opção.
    * Definir como o valor convertido deve ser arredondado.  
6. Clique em OK.
7. Feche a página.


