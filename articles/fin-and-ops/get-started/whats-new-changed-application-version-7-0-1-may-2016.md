---
title: "O que há de novo ou diferente no Dynamics AX versão 7.0.1 (maio de 2016)"
description: "Este artigo descreve os recursos novos ou alterados na versão 7.0.1 do Microsoft Dynamics AX. Esta versão foi lançada em maio de 2016 e tem um número de compilação 7.0.1265.23014."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b8e4f306d2ee20323229b478c93c1c7eeaba50be
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a>O que há de novo ou diferente no Dynamics AX versão 7.0.1 (maio de 2016)

[!include[banner](../includes/banner.md)]


Este artigo descreve os recursos novos ou alterados na versão 7.0.1 do Microsoft Dynamics AX. Esta versão foi lançada em maio de 2016 e tem um número de compilação 7.0.1265.23014.

<a name="electronic-reporting-er"></a>Relatório eletrônico (RE)
-------------------------

|                                                                                                                                                                                        |                                                                                                                                                                                                                                                                                                                                                        |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **O que você pode fazer?**                                                                                                                                                                   | **Por que isso é importante?**                                                                                                                                                                                                                                                                                                                             |
| Configure uma caixa de diálogo de tempo de execução para a criação de relatórios através do Relatório Eletrônico (RE), para que os usuários possam selecionar as dimensões financeiras desejadas.                                     | Em tempo de execução, na caixa de diálogo para executar um relatório de RE, os usuários podem selecionar várias dimensões financeiras. Os detalhes das dimensões financeiras selecionadas serão exibidos no documento eletrônico gerado.                                                                                                                              |
| Configure o acesso a múltiplas dimensões financeiras durante o design de um relatório de RE, através de um único mapeamento para a fonte de dados desejada.                                                  | A mesma configuração de relatório de ER pode ser usada para gerar documentos eletrônicos que apresentam dados transacionais com detalhes de dimensões financeiras, independentemente do número de dimensões financeiras que são selecionadas tanto pelo usuário quanto configuradas para a entidade legal atual ou instância.                                             |
| Configure um relatório do RE para inserir dados em colunas geradas dinamicamente de um documento eletrônico que é criado no formato de planilha OPENXML.                                           | Um relatório de RE pode inserir dados em uma planilha OPENXML gerada, por meio de replicação horizontal de colunas. Portanto, a mesma configuração de relatório de RE pode ser reutilizada para gerar documentos eletrônicos que possuem um número diferente de colunas geradas dinamicamente.                                                                                 |
| Configure destinos do RE para que o resultado de saída de um formato seja direcionado para um destino específico: arquivo, e-mail ou arquivamento (pasta Microsoft SharePoint ou Microsoft Azure Storage). | Anteriormente, ao executar uma configuração de RE, uma caixa de mensagem aparecia, solicitando uma ação de usuário para salvar ou abrir um arquivo. Agora é possível pré-configurar um destino para cada configuração de formato e para cada componente de saída (uma pasta ou um arquivo) separadamente. Os usuários que têm direitos de acesso apropriados também podem modificar as configurações de destino em tempo de execução. |

## <a name="pos--microsoft-dynamics-ax-retail"></a>PDV – Microsoft Dynamics AX Retail
|                                |                                                                                                                                                                                         |
|--------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **O que você pode fazer?**           | **Por que isso é importante?**                                                                                                                                                              |
| Use o navegador Google Chrome. | Os varejistas agora podem iniciar o Cloud POS através do navegador Chrome, podendo desfrutar de todas as funcionalidades disponíveis nas versões do Cloud POS para Microsoft Edge e Internet Explorer. |

## <a name="financial-reporting"></a>Relatórios financeiros
|                                                                     |                                                                                                                                                                                                                                                                                                                    |
|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **O que você pode fazer?**                                                | **Por que isso é importante?**                                                                                                                                                                                                                                                                                         |
| Reconstrua o mercado de dados de Relatórios financeiros.                          | Quando você move bancos de dados do Dynamics AX entre ambientes ou faz outras alterações invasivas ao ambiente, o banco de dados de relatórios financeiros pode ter que ser reconstruído. Um script do Windows PowerShell agora é fornecido para reconstruir o banco de dados para você.                                                                |
| Não é mais possível selecionar opções de designer de relatório que não são válidas. | Diversas opções de designer de relatório que foram usadas nas versões de mercado do Relator de gerenciamento não se aplicam a esta versão do Dynamics AX. Essas opções estavam relacionadas ao projeto, saída e vinculação do relatório financeiro. Essas opções foram removidas do designer de relatório financeiro para evitar erros de usuário. |

## <a name="financial-management"></a>Gerenciamento financeiro
|                                                            |                                                                  |
|------------------------------------------------------------|------------------------------------------------------------------|
| **O que você pode fazer?**                                       | **Por que isso é importante?**                                       |
| Gerar arquivos de pagamento positivos para pagamentos de contas a pagar. | Arquivos de pagamento positivos podem ser gerados para ajudar a evitar fraude de cheque. |

## <a name="warehouse-and-production"></a>Depósito e produção
|                                                                                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **O que você pode fazer?**                                                                                                                                                                                                                                                                                                                                                                    | **Por que isso é importante?**                                                                                                                                                                                                                                                                                                                                                                                                              |
| Defina uma política de trabalho do depósito que controla a criação de trabalho para um conjunto de produtos em locais específicos.                                                                                                                                                                                                                                                                          | Os processos de depósito nem sempre incluem o trabalho. Ao usar a nova política de trabalho do depósito, você pode impedir a criação de trabalho para a separação de matéria-prima e organização de mercadorias concluídas para um conjunto de produtos em locais específicos.                                                                                                                                                                                                     |
| Especifique que um local de saída da produção não é controlado pela placa do carro.                                                                                                                                                                                                                                                                                                               | Agora é possível especificar que um local de saída da produção não é controlado pela placa do carro. Por exemplo, esse recurso é útil quando uma ordem de produção reversa relata itens como concluídos diretamente para um local que atua como um local de entrada de produção para uma ordem de produção direta.                                                                                                                                                     |
| Suporte para BOMs que incluem itens com dimensões de produto diferentes para o mesmo item.                                                                                                                                                                                                                                                                                                     | Ao usar uma ou várias dimensões de produto na produção, podem ocorrer situações onde você gostaria de produzir um item, com base em uma variante diferente do mesmo item. Para obter mais informações, acesse [esse blog](https://blogs.msdn.microsoft.com/axmfg/2015/12/22/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item/).                                                                  |
| Ordens de produção com estruturas circulares no primeiro nível das suas BOMs são excluídas do cálculo de nível da BOM para o planejamento de recursos materiais.                                                                                                                                                                                                                                     | Não é possível atribuir níveis corretos da BOM para variantes de produto em ordens de produção que causam circularidade na hierarquia da BOM.                                                                                                                                                                                                                                                                                                  |
| Calcular níveis de lista de materiais separados para planejamento de recursos materiais e cálculo de custos: • Para planejamento de recursos materiais, os níveis de lista técnica são calculados na nova tabela **ReqItemLevel**. Ordens de produção finalizadas são ignoradas no cálculo. • Para o cálculo do custo de produção, os níveis da BOM são calculados em **InventTable**. Ordens de produção finalizadas são incluídas no cálculo. | • Ao executar o planejamento de recurso material, por exemplo, explosão e agendamento do plano de planejamento mestre, somente os níveis da BOM usados no planejamento de recurso material precisam ser recalculados. Em outras palavras, não é necessário calcular níveis da BOM usados no cálculo de custos de produção. • Ao executar operações de custos, por exemplo, fechamento de estoque, somente os níveis da BOM usados no cálculo de custos de produção precisam ser recalculados. |

 

<a name="see-also"></a>Consulte também
--------

[Novidades ou alterações](whats-new-changed.md)

[Guias de tarefas novos ou atualizados (maio de 2016)](new-updated-task-guides-available-may-2016.md)




