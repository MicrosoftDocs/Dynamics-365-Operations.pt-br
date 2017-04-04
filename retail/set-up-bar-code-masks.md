---
title: "Configurar máscaras de código de barras"
description: "Este tópico descreve como configurar caracteres de máscara de código de barras, máscaras de código de barras, e como atribuir máscaras de código de barras a códigos de barras."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fe598799d52cacd84da775ac7ace8cf9a30ae5fe
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bar-code-masks"></a>Configurar máscaras de código de barras

Este tópico descreve como configurar caracteres de máscara de código de barras, máscaras de código de barras, e como atribuir máscaras de código de barras a códigos de barras.

<a name="set-up-bar-code-mask-characters"></a>Configurar caracteres da máscara do código de barras
-------------------------------

Máscaras de código de barras são usados para criar códigos de barras e para identificar rapidamente os códigos de barras que são digitalizados de venda (POS). As máscaras são compreendidas de caracteres que atuam como espaços reservados que indiquem o formato dos códigos de barras que será criado. Para configurar uma máscara de código de barras, você precisará configurar caracteres de máscara de código de barras. Ir ** varejo e comércio ** &gt; ** gerenciamento de estoque ** &gt; ** códigos de barras e rótulos ** &gt; ** caracteres de máscara. ** ** ** Clique em novo para criar caracteres de máscara de código de barras. Os caracteres de máscara podem ser criados para indicar os seguintes dados do código de barras.

|                      |                                                                                                                 |
|----------------------|-----------------------------------------------------------------------------------------------------------------|
| **Field**            | **Description**                                                                                                 |
| **Product**          | O espaço reservado para a ID de produto.                                                                                     |
| **Any number**       | Usado para especificar um número gerado codificado rígido em códigos de barras.                                                  |
| **Check digit**      | Indica que o formato de código de barras em uma máscara de código de barras usado um dígito de verificação para garantir a validade de um código de barras. |
| **Size digit**       | Indica o tamanho em um código de barras criado para uma grade de produtos que incluam o tamanho.                                 |
| **Color digit**      | Indica a cor em um código de barras criado para uma grade de produtos que inclui cor.                               |
| **Style digit**      | Indica o estilo em um código de barras criado para uma grade de produtos com um estilo.                             |
| **EAN license code** | O espaço reservado para a licença EAN emitida para códigos de licença EAN.                                                       |
| **Preço**            | Indica o preço para códigos de barras inseridos preço.                                                                   |
| **Quantity**         | Indica a quantidade em peso aleatório quantidade/códigos de barras inseridos.                                                |
| **Employee**         | Indica o segmento de código de barras para o número de identificação de funcionário usado para fazer o logon POS de código de barras.                                  |
| **Customer**         | Indica o segmento de ID de cliente.                                                                                  |
| ** ** Entrada de dados       | *Not entanto implemented.*                                                                                          |
| **Discount code**    | Indica o código de desconto para um código de barras usado para adicionar um desconto para uma transação de venda de ponto             |
| **Vale-presente**        | Indica o número de vale-presente ao emitir ou ao por pagar vale-presente.                                               |
| **Loyalty card**     | Adicionar um cliente de fidelidade a transação, e pode ser usado ao pagar por fidelidade.                             |

## <a name="define-bar-code-masks"></a>Defina máscaras de código de barras
Depois dos caracteres de máscara de código de barras são especificados para necessárias máscaras de código de barras, vai ** varejo e comércio ** &gt; ** gerenciamento de estoque ** &gt; ** códigos de barras e rotulam ** &gt; ** configuração de máscara de código de barras **. Nesta página, é possível definir as máscaras de código de barras que usam os caracteres especificados anteriormente. As máscaras de código de barras será usada para gerar códigos de barras e também identificar ajudarão aos códigos de barras digitalizados no POS.

1.  ** ** Clique em novo para criar uma nova a máscara de código de barras.
2.  Insira valores em ** ID da máscara e ** ** descrição ** sobre campos, e selecione uma máscara de código de barras em tipo ** ** o campo.
3.  ** Geral ** na seção, selecione um valor em ** de código de barras padrão ** campo, e especifique o prefixo de código de barras, se um é necessário.
4.  ** Segmento de máscara de código de barras ** na seção, adicione os segmentos de código de barras que serão usadas no código de barras a ser criado.

Como exemplo, criar uma máscara de código de barras com a ID “produtos” máscara, você faria o seguinte:

1.  Criar novo máscara de código de barras e selecione o tipo “produtos”.
2.  Marque um padrão de código de barras, por exemplo, “39.” Código
3.  Forneça um prefixo a ser usado para identificar facilmente o código de barras. Por exemplo, “22 ".
4.  Adicionar um segmento de máscara. O segmento de máscara de produtos “” será selecionado.
5.  Forneça um comprimento do segmento de produto, por exemplo, “10 ". O período deve corresponder o tamanho de uma ID de produto comumente usado na loja. A máscara será exibida como uma visualização ** geral ** na seção abaixo ** ** máscara.

## <a name="assign-bar-code-masks-to-bar-codes"></a>Máscaras de código de barras de atribuir códigos de barras
As máscaras de códigos de barras devem ser atribuídas para códigos de barras para poderem ser usadas. Continuando com o exemplo anterior, a alocação da máscara de código de barras para um código de barras, faça o seguinte:

1.  Ir ** administração organizacional ** &gt; ** de instalação ** &gt; ** ** códigos de barras. ** ** Clique em novo para criar um novo código de barras.
2.  Insira valores em ** código de barras ** ** configuração ** e ** de instalação ** em campos.
3.  ** ** Em geral, a seção em ** tipo de código de barras ** campo, selecione o Código “39”. ** Máscara ** ** em ID ** campo, selecione a máscara de produtos “” criada anteriormente.
4.  ** ** Tamanho em, insira “12 ".
5.  Click **Save**.

A máscara de código de barras pode então ser usada para criar códigos de barras para produto. As etapas acima são exemplos de como criar máscaras de código de barras para produto, mas também ilustram como criar máscaras de código de barras para os outros tipos suporte de código de barras. As máscaras, os tipos, e os tamanhos de código de barras devem ser ajustados para uso em seu ambiente específico.


