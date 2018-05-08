---
title: "Configurar máscaras de código de barras"
description: "Este tópico descreve como configurar caracteres de máscara de código de barras, máscaras de código de barras e como atribuir máscaras de código de barras a códigos de barras."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e61524feab1b06f4a863a140b883bf8fe49af1e2
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-bar-code-masks"></a>Configurar máscaras de código de barras

[!include [banner](includes/banner.md)]

Este tópico descreve como configurar caracteres de máscara de código de barras, máscaras de código de barras e como atribuir máscaras de código de barras a códigos de barras.

<a name="set-up-bar-code-mask-characters"></a>Configurar caracteres da máscara do código de barras
-------------------------------

As máscaras de código de barras são usadas para criar códigos de barras e identificar rapidamente códigos de barras que são digitalizados para o ponto de venda (POS). As máscaras são compostas de caracteres que atuam como espaços reservados que indicam o formato dos códigos de barras que serão criados. Para configurar uma máscara de código de barras, é necessário configurar caracteres de máscara de código de barras. Vá para **Varejo** &gt; **Gerenciamento de estoque** &gt; **Códigos de barras e etiquetas** &gt; **Caracteres de máscara**. Clique em **Novo** para criar caracteres de máscara de código. Os caracteres de máscara podem ser criados para indicar os seguintes dados de código de barras.

|                      |                                                                                                                 |
|----------------------|-----------------------------------------------------------------------------------------------------------------|
| **Campo**            | **Descrição**                                                                                                 |
| **Produto**          | O espaço reservado para a ID de produto.                                                                                     |
| **Qualquer número**       | Usado para especificar um número que será codificado em códigos de barras.                                                  |
| **Dígito de verificação**      | Indica que o formato de código de barras em uma máscara de código de barras usa um dígito de verificação para garantir a validade de um código de barras. |
| **Dígito de tamanho**       | Indica o tamanho em um código de barras criado para uma variante de produto que inclui tamanho.                                 |
| **Dígito de cor**      | Indica a cor em um código de barras criado para uma variante de produto que inclui cor.                               |
| **Dígito de estilo**      | Indica o estilo em um código de barras criado para uma variante de produto que inclui um estilo.                             |
| **Código de licença EAN** | O espaço reservado para a licença EAN emitida para códigos de licença EAN.                                                       |
| **Preço**            | Indica o preço para códigos de barras de preço embutidos.                                                                   |
| **Quantidade**         | Indica a quantidade em códigos de barra embutidos de quantidade/peso aleatório.                                                |
| **Funcionário**         | Indica o segmento de código de barras para o número de identificação de funcionário usado para fazer o logon no POS de código de barras.                                  |
| **Cliente**         | Indica o segmento de ID do cliente.                                                                                  |
| **Inserção de dados**       | *Ainda não implementado.*                                                                                          |
| **Código de desconto**    | *Depreciado* a partir do 365 para a versão de varejo primavera 2017. Anteriormente: Indica código de desconto para um código de barras usado para adicionar um desconto a uma transação de ponto de venda                                                                   |
| **Código do cupom**      | Indica o código de cupom para um código de barras usado para adicionar um desconto em uma ordem de varejo. Isso substituiu o código de desconto.     |
| **Vale-presente**        | Indica um número de vale-presente ao emitir ou pagar por cartão de presente.                                               |
| **Cartão-fidelidade**     | Adiciona um cliente de fidelidade à transação e pode ser usado ao pagar por lealdade                             |

## <a name="define-bar-code-masks"></a>Definir máscaras de código de barras
Depois que os caracteres de máscara de código de barras forem especificados para as máscaras de código de barras necessárias, vá para **Varejo** &gt; **Gerenciamento de estoque** &gt; **Códigos de barras e rótulos** &gt; **Configuração de máscara de código de barras**. Nesta página, é possível definir as máscaras de código de barras que usam os caracteres especificados anteriormente. Essas máscaras de código de barras serão usadas ao gerar códigos de barras e também ajudarão a identificar códigos de barras digitalizados no POS.

1.  Clique em **Novo** para criar uma nova máscara de código de barras.
2.  Insira valores nos campos **ID da máscara** e **Descrição**, e selecione uma máscara de código de barras no campo **Tipo**.
3.  Na seção **Geral**, selecione um valor no campo **Código de barras padrão** e depois especifique o prefixo do código de barras, se for necessário uma nova máscara de código de barras.
4.  Na seção **Segmento de máscara de código de barras**, adicione os segmentos de código de barras que serão usados no código de barras a ser criado.

Como exemplo, crie uma máscara de código de barras com a ID de máscara “Produto", fazendo o seguinte:

1.  Crie uma nova máscara de código de barras e selecione o tipo "Produto".
2.  Selecione um código de barras padrão, por exemplo, "Código 39".
3.  Forneça um prefixo a ser usado para identificar facilmente o código de barras. Por exemplo, "22".
4.  Adicione um segmento de máscara. O segmento de máscara "Produto" será selecionado.
5.  Forneça um comprimento do segmento de produto, por exemplo, “10 ". O período deve corresponder o tamanho de uma ID de produto comumente usado na loja. A máscara será exibida como uma visualização na seção **Geral** em **Máscara**.

## <a name="assign-bar-code-masks-to-bar-codes"></a>Atribua máscaras de código de barras aos códigos de barras
As máscaras dos códigos de barras devem ser atribuídas aos códigos de barras antes de poderem ser utilizadas. Continuando com o exemplo anterior, para atribuir a máscara de código de barras a um código de barras, faça o seguinte:

1.  Vá para **Administração de organização** &gt; **Configuração** &gt; **Códigos de barras**. Clique em **Novo** para criar um novo código de barras.
2.  Insira os valores nos campos **Código de barras** **configuração** e **Configuração**.
3.  Na seção **Geral**, no campo **Tipo de código de barras**, selecione "Código 39". No campo **Máscara** **ID**, selecione a máscara de "Produto" criada anteriormente.
4.  Em **Tamanho**, digite "12".
5.  Clique em **Salvar**.

A máscara de código de barras agora pode ser usada para criar códigos de barras para produtos. As etapas acima são exemplos de como criar máscaras de código de barras para produtos, mas também ilustram como criar máscaras de código de barras para qualquer um dos outros tipos de códigos de barras suportados. As máscaras, tipos e comprimentos de código de barras devem ser ajustados para uso em seu ambiente específico.




