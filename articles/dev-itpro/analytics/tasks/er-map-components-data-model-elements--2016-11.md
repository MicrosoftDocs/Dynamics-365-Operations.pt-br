--- 
title: Mapear os componentes de formatos para elementos de modelo de dados
description: "O seguinte procedimento mostra como um usuário na função de Administrador do sistema ou desenvolvedor de Relatório eletrônico pode mapear elementos do modelo de dados para componentes da configuração de Relatório eletrônico (ER) criada, que define um formato de documento eletrônico para o domínio da empresa de pagamentos."
author: NickSelin
manager: AnnBe
ms.date: 02/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: e065cfbfc645bb7ac48134fe43d87bec013e8c81
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="map-the-components-of-formats-to-data-model-elements"></a>Mapear os componentes de formatos para elementos de modelo de dados

[!include [task guide banner](../../includes/task-guide-banner.md)]

O seguinte procedimento mostra como um usuário na função de Administrador do sistema ou desenvolvedor de Relatório eletrônico pode mapear elementos do modelo de dados para componentes da configuração de Relatório eletrônico (ER) criada, que define um formato de documento eletrônico para o domínio da empresa de pagamentos. Este formato será usado posteriormente para gerar documentos eletrônicos para processar pagamentos. Neste exemplo, você irá criar uma configuração de formato para a empresa exemplo, ‘Litware, Inc.’. Essas etapas podem ser realizadas em qualquer empresa uma vez que configurações de RE são compartilhadas para todas as empresas. Para concluir estas etapas, você deve primeiro concluir as etapas no guia de tarefas "Criar uma configuração de formato".


## <a name="select-a-format-configuration"></a>Selecione uma configuração de formato
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Clique em Configurações de relatórios.
3. Na árvore, expanda "Pagamentos (modelo simplificado)".
4. Na árvore, selecione "Pagamentos (modelo simplificado)\BACS (Reino Unido fictício)".
5. Clique em Designer.

## <a name="map-format-components-to-data-model-elements"></a>Mapear componentes do formato aos elementos do modelo de dados
1. Clique em Expandir/recolher.
2. Clique na aba Mapeamento.
3. Na árvore, expanda 'modelo'.
4. Na árvore, selecione "Xml\Mensagem\ProcessingDate\DateTime".
5. Na árvore, selecione "modelo\ProcessingDateTime".
6. Clique em Associar.
7. Na árvore, selecione "Xml\Mensagem\MessageId\String".
8. Na árvore, selecione "modelo\MessageIdentification".
9. Clique em Associar.
10. Na árvore, expanda 'modelo\Pagamentos'.
11. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Valor\String".
12. Na árvore, selecione "modelo\Pagamentos\InstructedAmount".
13. Clique em Associar.
14. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\TransDate\DateTime".
15. Na árvore, selecione "modelo\Pagamentos\TransactionDate".
16. Clique em Associar.
17. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Descrição\String".
18. Na árvore, selecione 'modelo\Pagamentos\Descrição'.
19. Clique em Associar.
20. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Moeda\String".
21. Na árvore, selecione 'modelo\Pagamentos\Moeda'.
22. Clique em Associar.
23. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Id".
24. Na árvore, selecione "modelo\Pagamentos\End2EndID".
25. Clique em Associar.
26. Na árvore, expanda 'modelo\Pagamentos\Credor'.
27. Na árvore, expanda 'modelo\Pagamentos\Credor\Conta'.
28. Na árvore, expanda 'modelo\Pagamentos\Credor\Agente'.
29. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Nome\String".
30. Na árvore, selecione 'modelo\Pagamentos\Credor\Nome'.
31. Clique em Associar.
32. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\RoutingNumber\String".
33. Na árvore, selecione "modelo\Pagamentos\Credor\Agente\RoutingNumber".
34. Clique em Associar.
35. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\AccountNumber\String".
36. Na árvore, selecione 'modelo\Pagamentos\Credor\Conta\Número'.
37. Clique em Associar.
38. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Nome\String".
39. Na árvore, expanda 'modelo\Pagamentos\Devedor'.
40. Na árvore, expanda 'modelo\Pagamentos\Devedor\Conta'.
41. Na árvore, expanda 'modelo\Pagamentos\Devedor\Agente'.
42. Na árvore, selecione 'modelo\Pagamentos\Devedor\Nome'.
43. Clique em Associar.
44. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Banco\RoutingNumber\String".
45. Na árvore, selecione "modelo\Pagamentos\Devedor\Agente\RoutingNumber".
46. Clique em Associar.
47. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Banco\AccountNumber\String".
48. Na árvore, selecione 'modelo\Pagamentos\Devedor\Conta\Número'.
49. Clique em Associar.
50. Na árvore, selecione "Xml\Mensagem\Pagamentos\Item".
51. Na árvore, selecione 'modelo\Pagamentos'.
52. Clique em Associar.
53. Clique em Salvar.

## <a name="validate-format-mapping"></a>Valide o mapeamento de formato
1. Clique em Validar.
    * Valide o novo mapeamento para garantir que todas as associações são aprovadas.  
2. Feche a página.

## <a name="change-status-of-the-current-version-of-format-configuration"></a>Altere o status da versão atual da configuração de formato
    * Nas próximas etapas, você irá alterar o status da configuração de formato de Rascunho para Concluído para torná-la disponível para geração de documento de pagamento.  
1. Clique em Alterar status.
2. Clique em Concluir.
3. No campo Descrição, digite um valor.
    * Por exemplo, "versão 1".  
4. Clique em OK.
5. Selecione a versão concluída da configuração atual.
    * Observe que a configuração será salva como versão concluída 1.1: versão 1 do formato baseado na versão 1 do modelo de dados.  

## <a name="define-effective-date-for-completed-version-of-format"></a>Definir a data efetiva para a versão concluída do formato
    * Cada versão do formato pode ser configurada como disponível para uso a partir de uma data determinada. Quando mais de uma versão do formato estiver ativa em uma determinada data, o formato mais recente (com base no número de versão) será selecionado para o uso. O valor da data da sessão é utilizado na seleção da versão apropriada.  

## <a name="restrict-access-to-created-format-from-companies"></a>Restrinja o acesso ao formato criado pelas empresas
1. Expanda a seção Códigos ISO de país/região.
    * Cada acesso ao formato pode ser restringido através da identificação de países/regiões específicos nos quais um formato é aplicável. Quando a lista de países/regiões de um formato específico estiver vazia, esse formato poderá ser usado em qualquer empresa. Quando alguns códigos de países/regiões ISO forem inseridos na lista de países/regiões, o formato somente pode ser usado nas empresas, se os endereços principais estiverem no país/região.  


