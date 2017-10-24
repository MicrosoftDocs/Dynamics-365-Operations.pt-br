---
title: "Previsões e orçamentos de projeto"
description: 
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ForecastModel, ProjYearEndProcess
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23501
ms.assetid: 4e6d1384-19a2-4232-b3f3-d2590c218bd7
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 32dd89d92a496d6601d1983dbc3c8e7e579ee0b3
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="project-forecasts-and-budgets"></a>Previsões e orçamentos de projeto

[!include[banner](../includes/banner.md)]




O Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, fornece duas maneiras de gerenciar e controlar os projetos: previsões de projeto e orçamentos de projeto. 

Use a previsão de projeto se sua organização tiver uma perspectiva operacional e focar em receitas e custos derivados de transações específicas. Use o orçamento de projeto se a sua organização for mais focada nos valores financeiros. 

As previsões de projeto e os orçamentos de projeto usando modelos de previsão para conter os valores projetados para as transações. 

Cada método tem suas vantagens. É necessário considerar os seguintes pontos antes de selecionar um método para sua organização.

|                           |                                                                                                                                                                                                                                                         |                                                                                                                                                                         |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           | **Previsões de projeto**                                                                                                                                                                                                                                 | **Orçamento de projeto**                                                                                                                                                   |
| **Alocação de período**     | Não é possível alocar explicitamente as transações durante um período fiscal. Em vez disso, a previsão e o controle de previsão são baseados na duração do projeto. Como as previsões são baseadas em uma data específica, você deve inferir o período da data. | Você pode alocar transações durante todo o projeto ou um período fiscal. Se você alocar durante um período, poderá optar por postergar valores não usados para o próximo período fiscal. |
| **Exibindo transações**  | Você pode exibir as transações nos formulários de previsão, onde é possível ver as previsões para toda a empresa e para todos os projetos, independentemente da hierarquia. Para focar em um projeto específico, você deve filtrar os dados.                                       | Você pode exibir as transações orçadas para uma única hierarquia de projetos. Portanto, isso significa que você pode ver os detalhes das transações de um projeto pai ou de seus subprojetos.                 |
| **Variáveis de transação** | Ao inserir transações de previsão, é possível usar cada atributo que existe para uma transação real. Isso permite fornecer mais detalhes sobre a previsão. Por exemplo, você pode inserir detalhes de quantidades, trabalhadores, itens ou propriedades de linha.         | Ao inserir os detalhes do orçamento, é possível apenas usar valores, categorias, e atividades.                                                                                    |
| **Segurança**              | A previsão é baseada nas transações que você insere nos formulários de previsão, e não envolve um mecanismo de controle de processos. Qualquer trabalhador com permissões para acessar um formulário de previsão pode revisar as informações sem aprovação.                                        | O orçamento utiliza o sistema de fluxo de trabalho, o qual permite gerenciar alterações e manter um histórico das revisões.                                                       |
| **Tipos de entrada**           | As entradas de transação de previsão são baseadas em número de unidades e custos e preços da unidade de vendas.                                                                                                                                                       | Os detalhes do orçamento são baseados em valores que são divididos entre custos e receitas.                                                                                        |
| **Modelos de previsão**       | Como cada previsão deve estar associada a um modelo, você pode criar vários modelos de previsão e também configurar submodelos.                                                                                                                               | O orçamento do projeto limita os modelos de previsão usados para fazer o orçamento. Menos modelos de previsão podem ajudar a aumentar a consistência nas projeções.                           |
| **Excedentes de custo**         | Você só pode permitir ou recusar a entrada de transações que causarão um excedente de custo.                                                                                                                                                                | O orçamento do projeto fornece opções adicionais de controle para os usuários. Você pode permitir avisos e excedentes.                                                                   |
| **Controle**               | O controle de previsão é executado usando a redução de previsão. Os valores reais são subtraídos dos saldos da transação de previsão sem trilha de auditoria. Isso pode dificultar o rastreamento de onde as transações reais ocorreram.                   | No controle de orçamento de projeto, os valores reais são subtraídos dos valores do orçamento restante. Isso proporciona uma trilha de auditoria clara.                                   |

## <a name="project-forecasts"></a>Previsões de projeto
Quando a previsão de projeto é usada, será possível inserir as transações de previsão em formulários de previsão para cada tipo de transação. Cada atributo que está disponível para uma transação real pode ser usado para uma transação de previsão—por exemplo, lucratividade de linha, atributos de linha, trabalhadores ou descrições. Você também pode projetar quanto tempo depois de incorrer em um custo que você vai faturar um cliente. 

As transações de previsão do projeto são baseadas em unidades e valores. 

Você deve associar cada previsão de projeto a um modelo de previsão. Ao inserir uma transação de previsão, um modelo de previsão é sugerido automaticamente. O modelo de previsão atua como um contêiner para as transações de previsão. 

Você pode designar modelos de previsão como submodelos para um módulo. Isso permite faturar por região, por período de tempo, ou por departamento. É possível copiar as transações de previsão em um modelo para criar um novo modelo, e também transferir as transações para a contabilidade. Como há uma relação de um para um entre uma previsão e um modelo, cada modelo de previsão torna-se um orçamento separado para um projeto. 

Os modelos de previsão podem usar a redução de previsão como mecanismo de controle de projetos. Na redução de previsão, as transações reais reduzem os saldos da transação de previsão. Contudo, como a redução de previsão é aplicada no projeto mais alto na hierarquia, ela fornece uma visão limitada das alterações na previsão. Por exemplo, se um trabalhador está associado a um subprojeto, as transações reais do trabalhador serão lançadas no projeto pai. Isso pode dificultar o monitoramento de alterações, pois você não pode determinar facilmente qual transação em qual subprojeto causou uma redução no valor de previsão. Portanto, é aconselhável criar uma cópia de um modelo de previsão para a redução de previsão a ser usada. Você pode usar relatórios para visualizar o que foi originalmente previsto. 

Você pode revisar, copiar, excluir, ou transferir previsões de projeto para um orçamento da contabilidade. No entanto, não há controle de processo. Qualquer trabalhador com permissão para um formulário de previsão pode fazer revisões sem revisar.

-   **Revisar** – Você pode fazer revisões em uma transação de previsão nos mesmos formulários em que as entradas originais foram feitas.
-   **Copiar ou excluir** – Ao copiar transações de previsão, você copia as linhas de transação de um modelo de previsão para outro. Quando você exclui uma previsão, exclui as transações de previsão de um modelo de previsão. Para delimitar as transações de previsão que são copiadas ou excluídas, selecione os tipos de transação específicos e as datas. Isso permite copiar ou excluir somente partes específicas de uma previsão.
-   **Transferir** – Quando você transfere uma previsão de projeto para um orçamento de contabilidade, transfere as transações de previsão de um modelo de previsão para um modelo de orçamento de contabilidade. É possível substituir qualquer transação transferida anteriormente no orçamento de contabilidade para a qual você transferir a previsão de projeto.

## <a name="project-budgets"></a>Orçamentos de projeto
O orçamento do projeto é um método mais simples do que a previsão, embora seja integrado a modelos de previsão. Usar um único formulário de inscrição para obter detalhes do orçamento original e das revisões, e permite que as projeções sejam baseadas apenas em valor, categoria ou atividade. 

No orçamento do projeto, todos os orçamentos originais e revisões devem ser enviados ao fluxo de trabalho do projeto para aprovação. Os fluxos de trabalho oferecem a você um maior controle sobre o processo e criam um registro de histórico de alteração. 

O orçamento do projeto é semelhante ao orçamento da contabilidade, mas pode ser configurado de forma mais simples e rápida. Várias opções de orçamento da contabilidade, como sequências numéricas ou moeda, não precisam ser configuradas separadamente para projetos.

Os orçamentos do projeto são associados automaticamente a dois modelos de previsão, um para o orçamento original e outro para o orçamento restante. Portanto, os relatórios baseados em modelos de previsão podem usar os dados de orçamento. Quando um orçamento do projeto é comprometido, o sistema cria as transações de previsão com base nos modelos associados, que são usados para gerar relatórios e controle.

## <a name="forecast-models"></a>Modelos de previsão
Os modelos de previsão tem uma hierarquia de uma única camada. Isso significa que uma previsão de projeto deve estar associada a um modelo de previsão.

Se você usar a previsão de projeto, pode identificar modelos como submodelos. Você pode então criar previsões por departamento, período de tempo ou região. Por exemplo, você pode criar um modelo de previsão para um ano e, em seguida, criar submodelos para as previsões das regiões nordeste, sudeste, noroeste e sudoeste enviadas pelos chefes regionais. Ao selecionar opções diferentes nos relatórios disponíveis, você pode ver informações pela previsão total ou por submodelo.




