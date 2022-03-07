---
title: ER Projetar modelo de dados de domínio específico
description: Este tópico descreve como criar uma nova configuração de relatório eletrônico (ER) que contém um modelo de dados para documentos de pagamento eletrônico.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 351c5a6624f7ee912c507a9f74324f4c8f61166b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755025"
---
# <a name="er-design-domain-specific-data-model"></a>ER Projetar modelo de dados de domínio específico

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório Eletrônico (RE) que contem um modelo de dados para os documentos de pagamento eletrônico. Esse modelo de dados será usado posteriormente como uma fonte de dados quando você criar o formato dos documentos de pagamento.

Neste exemplo, será criado uma configuração para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em qualquer empresa, uma vez que configurações de ER são compartilhadas entre todas as empresas. Para completar essas etapas, você deve primeiro completar as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.

    Selecione o provedor de configuração para a empresa de exemplo, "Litware, Inc." Se não visualizar este provedor de configuração, você deve primeiro concluir as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".  
    
2. Clique em Configurações de relatórios.

    Você irá criar uma configuração que contém um modelo de dados para documentos de pagamento eletrônico. Este modelo de dados será usado posteriormente como uma base de dados quando você criar o formato para os documentos de pagamento.  

## <a name="create-a-new-data-model-configuration"></a>Criar uma nova configuração de modelo de dados
1. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
2. No campo Nome, digite 'Pagamentos (modelo simplificado)'.
3. No campo Descrição, digite 'Configuração do modelo de pagamento'.

    O provedor de configuração ativo é automaticamente inserido aqui. Este provedor será capaz de manter essa configuração. Outros provedores podem usar esta configuração, mas não poderão mantê-la.  

4. Clique no botão "Criar configuração" para completar a tarefa de criação de configuração

## <a name="create-a-data-model"></a>Criar um modelo de dados
Você está criando um novo modelo de dados para a configuração selecionada. Essa versão de configuração terá um status de Rascunho.  
1. Clique em Designer.

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a>Definir a estrutura de participação de um participante em um processo de pagamento
1. Clique em Novo para abrir a caixa de diálogo suspensa.
2. No campo Nome, digite "Participante".
3. Clique em Adicionar.
4. Clique em Novo para abrir a caixa de diálogo suspensa.
5. No campo Nome, digite 'Nome'.
6. No campo Tipo de item, selecione 'String'.
7. Clique em Adicionar.
8. No campo Encontrar, digite "Participante".
9. Clique em Localizar anterior.

## <a name="define-the-bank-structure-for-this-model"></a>Definir a estrutura do banco para este modelo
1. Clique em Novo para abrir a caixa de diálogo suspensa.
2. No campo Nome, digite 'Agente'.
3. No campo Tipo de item, selecione 'Registro'.
4. Clique em Adicionar.
5. No campo Descrição, insira "Instituição financeira (por exemplo, um banco) que mantém uma conta para o participante (devedor/credor).".

    Instituição financeira (por exemplo, um banco) que mantém uma conta para o participante (devedor/credor).  

6. Clique em Novo para abrir a caixa de diálogo suspensa.
7. No campo Nome, digite 'Nome'. 
8. No campo Tipo de item, selecione 'String'.
9. Clique em Adicionar.
10. Clique em Novo para abrir a caixa de diálogo suspensa.
11. No campo Nome, digite 'SWIFT'.
12. Clique em Adicionar.
13. No campo Descrição, insira "Código de identificação do banco". 
14. Clique em Novo para abrir a caixa de diálogo suspensa.
15. No campo Nome, digite 'Número Identificador do banco'.
16. Clique em Adicionar.
17. No campo Descrição, insira "Número identificador do banco".
18. Clique em Localizar anterior.

## <a name="define-the-bank-account-structure-for-this-model"></a>Definir a estrutura da conta bancária para este modelo
1. Clique em Novo para abrir a caixa de diálogo suspensa.
2. No campo Nome, digite 'Conta'. 
3. No campo Tipo de item, selecione 'Registro'.
4. Clique em Adicionar.
5. No campo Descrição, insira "Identificação de uma conta do participante em uma instituição financeira (por exemplo, um banco)".

    Identificação de uma conta do participante em uma instituição financeira (por exemplo, um banco).  

6. Clique em Novo para abrir a caixa de diálogo suspensa.
7. No campo Nome, digite 'Moeda'. 
8. No campo Tipo de item, selecione 'String'.
9. Clique em Adicionar.
10. No campo Descrição, insira "Código de moeda".
11. Clique em Novo para abrir a caixa de diálogo suspensa.
12. No campo Nome, digite 'Número'. 
13. Clique em Adicionar.
14. Clique em Novo para abrir a caixa de diálogo suspensa.
15. No campo Nome, digite 'IBAN'. 
16. Clique em Adicionar.
17. No campo Descrição, insira "Número de conta bancária internacional".

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a>Definir a estrutura de mensagem de pagamento para o tipo de pagamento de transferência de crédito
1. Clique em Novo para abrir a caixa de diálogo suspensa.
2. No campo Novo nó como um, insira "Raiz do modelo".
3. No campo Nome, digite 'Início da Transferência de Crédito do Cliente'.
4. Clique em Adicionar.
5. No campo Encontrar, digite "CustomerCreditTransferInitiation". 
6. Clique em Localizar anterior.
7. Clique em Novo para abrir a caixa de diálogo suspensa.
8. No campo Nome, digite 'Identificação da Mensagem'. 
9. Clique em Adicionar.
10. No campo Descrição, insira "A referência ponto a ponto definida pelo participante instrutor (e enviada ao próximo participante) para identificar uma mensagem".

    A referência ponto a ponto atribuída pela parte instrutora (e enviada para o próximo participante) para identificar uma mensagem.  

11. Clique em Novo para abrir a caixa de diálogo suspensa.
12. No campo Nome, digite 'ProcessamentoDataHora'.
13. No campo Tipo de item, selecione 'DataHora'.
14. Clique em Adicionar.
15. No campo Descrição, insira "Data e hora em que a mensagem de pagamento foi criada". 
16. Clique em Novo para abrir a caixa de diálogo suspensa.

    Defina a estrutura da transação de pagamento para este modelo.  

17. No campo Nome, digite 'Pagamentos'.
18. No campo Tipo de item, selecione 'Lista de Registro'.
19. Clique em Adicionar.
20. No campo Descrição, insira 'Linhas de pagamento da mensagem atual'.
21. Clique em Novo para abrir a caixa de diálogo suspensa.
22. No campo Nome, digite 'Credor'. 
23. No campo Tipo de item, selecione 'Registro'.
24. Clique em Adicionar.
25. No campo Descrição, insira "Participante ao qual um valor em dinheiro é devido". 
26. Clique em Alternar referência de item.
27. No campo Encontrar, digite "Participante".
28. Clique em Localizar próximo.
29. Clique em OK.
30. No campo Encontrar, digite "Pagamentos".
31. Clique em Localizar próximo.
32. Clique em Novo para abrir a caixa de diálogo suspensa.
33. No campo Nome, digite 'Devedor'. 
34. Clique em Adicionar.
35. No campo Descrição, insira "Participante que deve um valor em dinheiro ao credor (definitivo)".
36. Clique em Alternar referência de item.
37. No campo Encontrar, digite "Participante".
38. Clique em Localizar próximo.
39. Clique em OK.
40. Clique em Localizar próximo.
41. Clique em Novo para abrir a caixa de diálogo suspensa.
42. No campo Nome, digite 'Descrição'.
43. No campo Tipo de item, selecione 'String'.
44. Clique em Adicionar.
45. Clique em Novo para abrir a caixa de diálogo suspensa.
46. No campo Nome, digite 'Moeda'.
47. Clique em Adicionar.
48. No campo Descrição, insira "Código de moeda".
49. Clique em Novo para abrir a caixa de diálogo suspensa.
50. No campo Nome, digite 'Data da Transação'. 
51. No campo Tipo de item, selecione 'Data'.
52. Clique em Adicionar.
53. No campo Descrição, insira "Data da transação". 
54. Clique em Novo para abrir a caixa de diálogo suspensa.
55. No campo Nome, digite 'Quantia Indicada'.  
56. No campo Tipo de item, selecione 'Real'.
57. Clique em Adicionar.
58. No campo Descrição, insira "O valor em dinheiro a ser movimentado entre o devedor e o credor, antes da dedução dos encargos". O valor deve ser expresso na moeda definida pela parte que inicializou a transação.'.

    O valor em dinheiro a ser movido entre o devedor e o credor, antes da dedução dos encargos. O valor deve ser expresso na moeda definida pela parte que inicializou a transação.  

59. Clique em Novo para abrir a caixa de diálogo suspensa.
60. No campo Nome, digite 'End2EndID'. 
61. No campo Tipo de item, selecione 'String'.
62. Clique em Adicionar.
63. No campo Descrição, insira "A identificação exclusiva atribuída pelo participante que inicializou a transação". Essa identificação é transmitida, inalterada, ao longo de toda a cadeia ponto-a-ponto.'. 
64. No campo Nome, digite 'Modelo de Pagamento'.

    O nome do PaymentModel se alinha a interfaces predefinidas de formulários de pagamento.  

65. Clique em Salvar.
66. Feche a página.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]