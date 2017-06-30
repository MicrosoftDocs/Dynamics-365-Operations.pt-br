---
title: "Configurar um modelo de configuração do produto"
description: "Este artigo descreve as etapas para configurar e criar um modelo de configuração do produto."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 4051
ms.assetid: 00df5537-b148-4e32-a248-3e35876ad4e1
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 8307ad3be2bc2799abdf057123b6022c7032b191
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-a-product-configuration-model"></a>Configurar um modelo de configuração do produto

[!include[banner](../includes/banner.md)]


Este artigo descreve as etapas para configurar e criar um modelo de configuração do produto.

| Tarefa                                                        | descrição                                                                                                                                                                                                                                                                                                                                                                                        |
|-------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Criar um produto mestre.                                    | Crie um produto mestre da lista **Produto mestre**. Libere o mestre do produto para todas as empresas relevantes. Para um produto mestre que é usado como uma versão para um modelo de configuração de produto ou como um subcomponente, a opção **Configuração baseada em restrição** deve ser selecionada como a tecnologia de configuração, e a dimensão de configuração deve estar selecionada somente para o grupo de dimensões do produto. |
| Criar componentes.                                          | Crie os componentes na página **Componentes**. Os componentes são os blocos de construção de um modelo de configuração de produtos, e podem ser reutilizados em vários modelos de configuração de produtos.                                                                                                                                                                                                                      |
| Criar tipos de atributos.                                     | Crie tipos de atributos na página **Tipos de atributos**. Os tipos de atributos especificam o conjunto de tipos de dados para todos os atributos que são usados nos modelos de configuração do produto. Atributos **Boolianos**, de **Texto** com uma lista fixa e **Inteiro** com tipos de intervalor listam o conjunto de valores disponíveis quando você configura uma variante do produto com base em um modelo de configuração do produto.       |
| Criar um modelo de configuração do produto.                       | Crie um modelo de configuração do produto na página **Novo modelo de configuração do produto**.                                                                                                                                                                                                                                                                                                              |
| Adicionar atributos a um modelo de configuração do produto.            | Crie um atributo na Guia Rápida **Atributos** na página **Detalhes do modelo de configuração do produto baseada em restrições**. Os atributos descrevem os recursos do modelo de configuração de produtos.                                                                                                                                                                                                       |
| Adicionar restrições a um modelo de configuração do produto.           | Crie restrições na Guia Rápida **Restrições** na página **Detalhes do modelo de configuração do produto baseada em restrições**. As restrições são limitações que uma configuração do produto deve atender. As restrições são restrições de expressão ou de tabela.                                                                                                                                 |
| Adicionar subcomponentes a um modelo de configuração de produto.         | Crie subcomponentes na Guia Rápida **Subcomponentes** na página **Detalhes do modelo de configuração do produto baseada em restrições**. Os subcomponentes estão relacionados a componentes e são vinculados a itens que representam o subcomponente.                                                                                                                                                                       |
| Adicionar requisitos de usuário a um modelo de configuração de produtos.     | Os requisitos de usuário são semelhantes aos subcomponentes, mas não fazem referência a um item. Pense sobre os requisitos do usuário como uma BOM fantasma. Todas as linhas da BOM ou operações de roteiro que são colocadas diretamente no requisito de usuário serão tomadas no componente principal.                                                                                                                       |
| Adicionar linhas da BOM a um modelo de configuração de produto.             | Crie linhas de BOM na Guia Rápida **Linhas de BOM** na página **Detalhes do modelo de configuração do produto baseada em restrições**. As linhas de BOM representam uma parte necessária para compilar uma variante do produto.                                                                                                                                                                                                 |
| Adicionar operações de roteiro a um modelo de configuração do produto.      | Crie operações de roteiro na Guia Rápida **Operações de roteiro** na página **Detalhes do modelo de configuração do produto baseada em restrições**. As operações de roteiro representam uma etapa em uma sequência de etapas executadas para criar uma variante do produto.                                                                                                                                                    |
| Criar uma versão ativa de um modelo de configuração do produto. | Crie uma versão ativa do modelo de configuração do produto na página **Versões**. Uma versão é o relacionamento entre um modelo de configuração de produtos e um produto mestre. Um modelo de configuração de produtos com uma versão ativa pode ser configurado a partir de uma ordem de venda, cotação de venda, ordem de compra ou ordem de produção.                                                               |
| Testar um modelo de configuração do produto.                         | Teste o modelo de configuração do produto da página **Detalhes do modelo de configuração do produto baseada em restrições** ou na página **Lista de modelos de configuração do produto**. O teste dos modelos de configuração de produtos simula o processo de configuração de modelo do produto que ocorre durante o manuseio da ordem.                                                                                                |
| Criar um modelo do modelo de configuração de produto.                | Crie um modelo do modelo de configuração do produto na página **Modelos de configuração**. Um modelo de configuração inclui valores de atributos no modelo de configuração de produtos. Selecione os valores de atributo na página **Configurar linha**. Você pode optar por carregar um modelo de configuração do modelo do produto durante a configuração do modelo do produto.                                                   |
| Configurar um item.                                          | Os modelos de configuração do produto podem ser configurados a partir de uma ordem de venda, cotação de venda, ordem de compra ou ordem de produção.                                                                                                                                                                                                                                                                           |






