---
title: Operações de ponto de venda (PDV) online e offline
description: Este tópico fornece detalhes sobre as operações de ponto de venda (PDV) no Dynamics 365 Commerce. Ele especifica em que ponto do aplicativo as operações podem ser invocadas, e se estão disponíveis no modo offline.
author: jblucher
manager: AnnBe
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-09-27
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 7dc9f85bf90e6ddf9badf656eb136e28a71b036f
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594104"
---
# <a name="online-and-offline-point-of-sale-pos-operations"></a>Operações de ponto de venda (PDV) online e offline

[!include [banner](includes/banner.md)]

A maioria das ações tomadas pelo usuário no ponto de venda (POS) são consideradas operações. As operações são configuradas e gerenciadas no back office do Dynamics 365 Commerce. Várias operações podem ser adicionadas a botões na grade de botões PDV. Os usuários podem selecionar os botões para chamar as operações e executar sua função. Outras operações são parte do aplicativo principal de PDV, e são invocadas de botões na tela ou como parte de outros fluxos de trabalho ou processos.

A tabela a seguir fornece detalhes sobre as operações que estão disponíveis no Modern POS e PDV em Nuvem. A tabela também especifica em que ponto do aplicativo as operações podem ser invocadas, e se estão disponíveis quando o PDV está em modo offline.

Algumas operações não estão disponíveis no momento no Modern POS ou PDV em Nuvem. Algumas dessas operações são específicas de localidade, e exigem extensões e configurações adicionais. Outros recursos são do Microsoft Dynamics AX 2012 que estão sem suporte no momento.

As seguintes colunas especificam onde as operações podem ser invocados:

- **Grade de botões** – A operação pode ser atribuída a botões em grades de botões PDV, que fazem parte de um layout da tela PDV.
- **Tela de transação** – A operação pode ser invocada de grades de botões PDV configuradas na tela de transação PDV.
- **Tela de boas-vindas** – A operação pode ser invocada de grades de botões PDV configuradas na tela de boas-vindas PDV.

> [!NOTE]
> As operações listadas a seguir se aplicam à versão mais recente do Commerce. Algumas operações podem ter mudado ou podem não estar disponíveis nas versões anteriores.

| ID | Operação | descrição | Grade de botões | Tela de transação | Tela de boas-vindas | Offline disponível | Específico de localidade |
|----|-----------|-------------|-------------|--------------------|----------------|-------------------|-----------------|
| 707 | Ativar dispositivo | Ativar o dispositivo atual para que um usuário autenticado forneça informações de conexão e atribua uma identificação do dispositivo e do registro. | Não | Não | Não | Não | Não |
| 134 | Adicionar afiliação | Adicione uma afiliação pré-selecionada a uma transação. Selecione a afiliação na página **Propriedades do botão**. | Sim | Sim | Não | Sim | Não |
| 135 | Adicionar afiliação da lista | Adicionar uma afiliação a uma transação selecionando-a em uma lista. | Sim | Sim | Sim | Sim | Não |
| 137 | Adicionar afiliação ao cliente | Adicione uma afiliação a um cliente na página **Detalhes do cliente**. | Não | Não | Não | Sim | Não |
| 138 | Remover afiliação do cliente | Remova uma afiliação na página **Detalhes do cliente**. | Não | Não | Não | Sim | Não |
| 643 | Adicionar código do cupom | Adicionar um cupom inserindo seu código no PDV. | Sim | Sim | Não | Sim | Não |
| 141 | Adicionar encargos de cabeçalho | Adicionar um encargo diverso ao cabeçalho da ordem. | Sim | Sim | Não | Não| Não |
| 141 | Adicionar encargos de linha | Adicionar um encargo diverso a uma linha de venda selecionada. | Sim | Sim | Não | Não| Não |
| 117 | Adicionar cartão de fidelidade | Solicitar que o usuário insira um número de cartão-fidelidade que será adicionado à transação atual. | Sim | Sim | Não | Sim | Não |
| 136 | Adicionar número de série | Esta operação permite ao usuário especificar um número de série para os produtos selecionados no momento. | Sim | Sim | Não | Sim | Não |
| 1214 | Adicionar Endereço de Remessa | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Não |
| 519 | Adicionar ao cartão-presente | Adicionar dinheiro ao vale-presente especificado. | Sim | Sim | Não | Não | Não |
| 6000 | Permitir ignorar o registro fiscal | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Sim |
| 1212 | Sangria para banco | Registrar o valor de dinheiro enviado ao banco e outras informações, como o número do malote bancário. | Sim | Sim | Sim | Sim | Não |
| 923 | Verificação dos totais bancários | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Sim |
| 915 | Operação em Branco | Essa operação representa um botão personalizável que um desenvolvedor de software pode alterar de forma programática para qualquer operação especializada exigida pela empresa. | Sim | Sim | Sim | Sim | Não |
| 1053 | Turno com fechamento cego | Definir o turno atual como fechamento cego, e desconectar o usuário. Um turno de fechamento cego é fechado para transações adicionais, mas ainda está aberto para operações de sacador, como a remoção e a declaração de meio de pagamento. | Sim | Sim | Sim | Não | Não |
| 310 | Calcular total | Quando o cálculo de desconto é adiado, esta operação inicia o cálculo da transação atual. | Sim | Sim | Não | Sim | Não |
| 642 | Executar Todos os Produtos | Definir o modo de entrega para todas as linhas como **Execução**. | Sim | Sim | Não | Sim\* | Não |
| 641 | Executar os Produtos Selecionados | Definir o modo de entrega para as linhas selecionadas como **Execução**. | Sim | Sim | Não | Sim\* | Não |
| 647 | Alterar modo de entrega | Alterar modo de entrega para linhas de venda pré-configuradas. | Sim | Sim | Não | Não| Não |
| 1215 | Alterar senha | Esta operação permite ao usuário PDV alterar sua senha. | Sim | Sim | Sim | Não | Não |
| 123 | Alterar Unidade de Medida | Alterar a unidade de medida para o item de linha selecionado. | Sim | Sim | Não | Sim | Não |
| 639 | Limpar representante de vendas padrão na transação | Remover o grupo de vendas por comissão (representante de vendas) da transação. | Sim | Sim | Não | Sim | Não |
| 106 | Limpar quantidade | Redefinir a quantidade na linha selecionada atual como **1**. | Sim | Sim | Não | Sim | Não |
| 640 | Limpar representante de vendas na linha | Remover o grupo de vendas por comissão (representante de venda) da linha selecionada no momento. | Sim | Sim | Não | Sim | Não |
| 121 | Limpar Vendedor | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Não |
| 1055 | Fechar turno | Fechar o turno atual, imprimir um relatório Z e desconectar o usuário do sistema. | Sim | Sim | Sim | Não | Não |
| 139 | Concluir transação | Pede ao usuário para selecionar o método do pagamento | Sim | Sim | Não | Sim | Não |
| 620 | Criar ordem do cliente | Converter a transação de PDV em uma ordem de cliente. | Sim | Sim | Não | Sim\* | Não |
| 925 | Copiar o cheque bancário | Esta operação não tem suporte. | Não aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Sim |
| 620 | Criar ordem do cliente | Converter a transação de PDV em uma ordem de cliente. | Sim | Sim | Não | Sim\* | Não |
| 621 | Criar cotação | Converter a transação de PDV em uma cotação de venda. | Sim | Sim | Não | Sim\* | Não |
| 636 | Criar transação de varejo | Esta operação permite que o usuário crie uma transação de venda padrão quando o comportamento padrão de PDV é criar ordens de cliente. | Sim | Sim | Não | Sim | Não |
| 600 | Cliente | Adicionar o cliente especificado à transação. | Não | Não | Não | Sim | Não |
| 1100 | Depósito na Conta do Cliente | Faça um pagamento em uma conta do cliente. | Sim | Sim | Sim | Sim | Sim |
| 612 | Adicionar Cliente | Esta operação permite que o usuário crie um novo registro de cliente. | Sim | Sim | Sim | Sim† | Não |
| 603 | Limpar Cliente | Remover o cliente da transação atual | Sim | Sim | Não | Sim | Não |
| 602 | Pesquisa de Cliente | Esta operação permite que o usuário busque um registro de cliente navegando até a página de pesquisa do cliente no PDV. | Sim | Sim | Sim | Sim | Não |
| 609 | Transações do Cliente | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Não |
| 917 | Status de conexão do banco de dados | Esta operação permite ao usuário exibir as configurações atuais de conexão, e alternar entre os modos online e offline. | Sim | Sim | Sim | Sim | Não |
| 1200 | Declarar Valor Inicial | Declarar o valor que está na caixa registradora quando o dia ou o turno se inicia. | Sim | Sim | Sim | Sim | Não |
| 132 | Substituição de depósito | Substituir o depósito padrão para ordens do cliente. | Sim | Sim | Não | Sim\* | Não |
| 913 | Desabilitar Modo de Design | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Não |
| 912 | Habilitar Modo de Design | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Não |
| 1217 | Kits de desmontagem | Desmonte um kit em seus produtos de componente. | Sim | Sim | Sim | Sim | Não |
| 624 | Exibir valores de reembolso | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Sim |
| 513 | Exibir Total | Mostrar o saldo da transação na exibição do cliente. | Sim | Sim | Sim | Sim | Não |
| 623 | Editar cliente | Editar os detalhes do cliente atual. | Sim | Sim | Não | Não | Não |
| 614 | Editar ordem do cliente | Cancelar a ordem selecionada para que possa ser alterada no PDV. | Não | Não | Não | Não | Não |
| 615 | Editar cotação | Cancelar a cotação selecionada para que possa ser alterada no PDV. | Não | Não | Não | Não | Não |
| 518 | Contas de Despesa | Registrar dinheiro que é removido da caixa registradora para despesas ocasionais. | Sim | Sim | Sim | Sim | Não |
| 919 | Logon estendido | Atribuir ou remover permissão para entrar digitalizando um código de barras ou passando um cartão. | Sim | Sim | Sim | Sim | Não |
| 1201 | Suprimento | Esta operação permite que o usuário adicione dinheiro na gaveta ou turno atual. | Sim | Sim | Sim | Sim | Não |
| 1218 | Forçar desbloqueio de periférico | O sistema usa essa operação internamente para desbloquear periféricos PDV. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Não |
| 520 | Saldo do cartão-presente | Mostrar o saldo de um vale-presente. | Sim | Sim | Não | Não | Não |
| 708 | Desativar dispositivo | Desativar o dispositivo atual, de modo que não possa ser usado como um registro PDV. | Não | Não | Não | Não | Não |
| 804 | Operação de entrada | Acessar os recursos do gerenciamento de estoque de armazenamento de entrada. | Sim | Não | Sim | Não| Não |
| 517 | Contas de Receita | Registrar dinheiro que é colocado na caixa registradora por um motivo diferente de uma venda. | Sim | Sim | Sim | Sim | Não |
| 801 | Pesquisa de estoque | Pesquisa disponível, na ordem, e quantidades de ATP (disponível para promessa) para a loja atual e outros locais disponíveis. | Sim | Sim | Sim | Não | Não |
| 122 | Comentário da fatura | Esta operação permite que o usuário insira um comentário sobre a transação atual. | Sim | Sim | Não | Sim | Não |
| 511 | Emitir Memorando de Crédito | Emitir um memorando de crédito para fornecer um comprovante, e não um reembolso. | Sim | Sim | Não | Não | Não |
| 512 | Emitir vale-presente | Emitir um novo vale-presente para o valor especificado. | Sim | Sim | Não | Não | Não |
| 625 | Emitir cartão-fidelidade | Emitir um cartão-fidelidade para um cliente, de forma que ele possa participar do programa de fidelidade da loja. | Sim | Sim | Sim | Não | Não |
| 300 | Valor do Desconto de Linha | Insira um valor de desconto para um item de linha na transação. Essa operação é usada apenas para itens com descontos e somente nos limites de desconto especificados. | Sim | Sim | Não | Sim | Não |
| 301 | Porcentagem do desconto de linha | Inserir uma porcentagem de desconto para um item de linha na transação. Essa operação é usada apenas para itens com descontos e somente nos limites de desconto especificados. | Sim | Sim | Não | Sim | Não |
| 703 | Bloquear registradora | Bloquear o registro atual, de modo que ele não possa ser usado, mas não desconectar o usuário atual. | Não | Não | Não | Sim | Não |
| 701 | Logoff | Desconectar o usuário atual do registro. | Sim | Sim | Sim | Sim | Não |
| 521 | Saldo de pontos do cartão-fidelidade | Mostrar o saldo dos pontos para o cartão-fidelidade especificado. | Sim | Sim | Não | Não | Não |
| 142 | Gerenciar encargos | Exibir e gerenciar encargos diversos aplicados à transação. | Sim | Sim | Não | Não| Não |
| 918 | Gerenciar turnos | Mostrar uma lista de turnos ativos, suspensos e fechados em branco. | Sim | Sim | Sim | Não | Não |
| 914 | Minimizar janela do POS | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Não |
| 1000 | Abrir Gaveta | Executar uma operação “sem venda" e abrir a gaveta do caixa atualmente selecionada. | Sim | Sim | Sim | Sim | Não |
| 928 | Cumprimento da ordem | Esta operação permite que os usuários escolham, embalem, enviem, ou cancelem ordens para retirada do armazenamento. | Sim | Sim | Sim | Não | Não |
| 805 | Operação de saída | Acessar recursos para gerenciar remessas de pedidos de transferência de saída. | Sim | Não | Sim | Não| Não |
| 129 | Substituir imposto do produto de linha | Substituir o imposto sobre o item de linha selecionado e usar outro imposto especificado. | Sim | Sim | Não | Sim | Não |
| 130 | Substituir imposto do produto de linha na lista | Substituir o imposto sobre o item de linha selecionado e usar o imposto que o usuário selecionar em uma lista. | Sim | Sim | Não | Sim | Não |
| 127 | Substituir imposto da transação | Substituir o imposto sobre a transação e usar outro imposto especificado. | Sim | Sim | Não | Sim | Não |
| 128 | Substituir imposto da transação na lista | Substituir o imposto sobre a transação e usar o imposto que o usuário selecionar em uma lista. | Sim | Sim | Não | Sim | Não |
| 131 | Guia de Remessa | Criar uma guia de remessa da ordem selecionada. | Não | Não | Não | Não | Não |
| 710 | Emparelhar estação de hardware | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Não |
| 201 | Pagar Cartão | Aceitar um cartão como cartão de crédito ou de débito como pagamento. | Sim | Sim | Não | Sim | Não |
| 200 | Pagar em dinheiro | Aceitar dinheiro como pagamento. | Sim | Sim | Não | Sim | Não |
| 206 | Pagar via dinheiro rápido | Concluir a transação em um toque, e aceitar o valor devido em dinheiro (troco exato). | Sim | Sim | Não | Sim | Não |
| 204 | Pagar Cheque | Aceite um cheque como pagamento. | Sim | Sim | Não | Sim | Não |
| 213 | Pagar Memorando de Crédito | Aceitar um memorando de crédito (comprovante) que foi emitido pela loja. | Sim | Sim | Não | Não | Não |
| 203 | Pagar Moeda | Aceitar pagamento em várias moedas. | Sim | Sim | Não | Sim | Não |
| 202 | Pagar Conta de Cliente | Cobrar a transação na conta do cliente. Este método de pagamento não é válido para depósitos da ordem de cliente. | Sim | Sim | Não | Não | Não |
| 214 | Pagar cartão-presente | Aceitar um cartão-presente emitido pela loja. | Sim | Sim | Não | Não | Não |
| 207 | Pagar cartão-fidelidade | Aceitar um cartão-fidelidade para pagamento, e resgatar os pontos para produtos qualificados. | Sim | Sim | Não | Não | Não |
| 634 | Histórico de pagamentos | Mostrar o histórico de pagamentos do cliente para a ordem atual do cliente. | Sim | Sim | Não | Não | Não |
| 803 | Separação e Recebimento | Abrir a página **Separação e recebimento**, onde é possível selecionar ordens para retirar ou receber na loja. | Sim | Sim | Sim | Não | Não |
| 632 | Separar todos os produtos | Definir o método de orçamento como **Retirada da loja** para todas as linhas. | Sim | Sim | Não | Sim\* | Não |
| 631 | Retirar produtos selecionados | Definir o método de orçamento como **Retirada da loja** para linhas selecionadas. | Sim | Sim | Não | Sim\* | Não |
| 400 | Menu Popup | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Não |
| 101 | Verificação de Preço | Esta operação permite que o usuário pesquise o preço de um produto especificado. | Sim | Sim | Sim | Sim | Não |
| 104 | Definição de Preço Manual | Substituir o preço de um produto se ele tiver sido configurado para permitir substituições de preço. | Sim | Sim | Não | Sim | Não |
| 1058 | Leitura X | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Sim |
| 1059 | Redução Z | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Sim |
| 927 | Imprimir etiqueta para item | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Não |
| 926 | Imprimir etiqueta para prateleira | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Não |
| 1056 | Imprimir X | Imprimir um relatório X para o turno atual | Sim | Sim | Sim | Não | Não |
| 103 | Comentário sobre o produto | Adicionar um comentário ao item de linha selecionado na transação. | Sim | Sim | Não | Sim | Não |
| 100 | Venda do produto | Adicionar um produto especificado à transação. | Sim | Sim | Sim | Sim | Não |
| 108 | Pesquisa de produtos | Esta operação permite que o usuário busque um produto navegando até a página de pesquisa do produto no PDV. | Sim | Sim | Sim | Sim | Não |
| 633 | Data de vencimento da cotação | Esta operação permite que o usuário exiba ou modifique a data de vencimento em uma cotação de venda. | Sim | Sim | Não | Sim\* | Não |
| 627 | Recalcular | Recalcular todas as linhas e impostos de ordens de cliente, com base na configuração atual. | Sim | Sim | Não | Sim\* | Não |
| 143 | Recalcular encargos | Recalcular os encargos automáticos aplicados ao pedido. | Sim | Sim | Não | Não| Não |
| 515 | Cancelar ordem | Esta operação permite ao usuário procurar e recuperar ordens de clientes e cotações de venda. | Sim | Sim | Sim | Não | Não |
| 504 | Recuperar Transação | Esta operação permite ao usuário recuperar uma transação suspensa anteriormente na loja atual. | Sim | Sim | Não | Sim‡ | Não |
| 305 | Resgatar pontos de fidelidade | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Sim |
| 635 | Reembolsar encargos de remessa | Esta operação permite ao usuário reembolsar encargos de remessa em uma ordem cancelada. | Não | Não | Não | Não | Não |
| 644 | Remover código do cupom | Solicitar que o usuário remova cupons selecionando-os em uma lista de cupons associados no momento à transação. | Sim | Sim | Não | Sim | Não |
| 1057 | Reimprimir Z | Reimprimir o relatório Z do deslocamento anterior ou de um turno selecionado. | Sim | Sim | Sim | Não | Não |
| 1216 | Insira uma nova senha | Esta operação permite ao usuário com a permissão de redefinição de senha redefinir outra senha de funcionário usando uma senha temporária. | Sim | Sim | Sim | Não | Não |
| 1219 | Abrir URL no POS | Esta operação deixa um usuário abrir uma URL configurada por admin no POS. | Sim | Sim | Sim | Sim | Não | 
| 109 | Devolver produto | Executar uma devolução de produtos individuais. O próximo produto verificado é mostrado como produto devolvido com quantidade e preço negativos. | Sim | Sim | Não | Sim | Não |
| 114 | Transação de Devolução | Cancelar uma transação prévia pelo número de recibo para retornar um ou todos os produtos. | Sim | Sim | Sim | Sim§ | Não |
| 1211 | Sangria para cofre | Realizar um depósito no cofre para mover o dinheiro da registradora para um cofre. | Sim | Sim | Sim | Sim | Não |
| 516 | Fatura de venda | Esta operação permite que o cliente efetue pagamentos da fatura selecionada. | Sim | Sim | Não | Não | Não |
| 502 | Vendedor | Esta operação permite ao usuário definir o valor **Tomador de vendas** em uma ordem de venda para as ordens do cliente no PDV. | Sim | Sim | Não | Sim\* | Não |
| 2000 | Gerenciamento de agenda | Ainda não há suporte para esta operação. | Sim | Sim | Sim | Não | Não |
| 2001 | Solicitações de agenda | Ainda não há suporte para esta operação. | Sim | Sim | Sim | Não | Não |
| 622 | Pesquisar | Esta operação permite aos usuários pré-configurar botões do PDV para executar pesquisas por item, cliente ou categoria. | Sim | Sim | Sim | Sim | Não |
| 1213 | Pesquisar Endereço de Remessa | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Não |
| 709 | Selecionar estação de hardware | Esta operação permite ao usuário selecionar uma estação de hardware em uma lista de estações disponíveis de hardware. | Sim | Sim | Sim | Sim | Não |
| 637 | Definir representante de vendas padrão na transação | Esta operação permite ao usuário selecionar um dos grupos qualificáveis de vendas por comissão (representantes de venda) como o representante de venda padrão para linhas que são adicionados posteriormente. | Sim | Sim | Não | Sim | Não |
| 105 | Definir Quantidade | Alterar a quantidade de um item de linha na transação. | Sim | Sim | Não | Sim | Não |
| 638 | Definir representante de vendas na linha | Esta operação permite ao usuário selecionar um dos grupos qualificáveis de vendas por comissão (representantes de venda) para a linha selecionada no momento. | Sim | Sim | Não | Sim | Não |
| 630 | Remeter todos os produtos | Definir o modo de atendimento como **Enviar** para todas as linhas de item. | Sim | Sim | Não | Sim\* | Não |
| 629 | Remeter produtos selecionados | Definir o modo de atendimento como **Enviar** para as linhas selecionadas. | Sim | Sim | Não | Sim\* | Não |
| 115 | Mostrar Diário | Mostrar o diário da loja. Você pode exibir transações, reimprimir recibos e recibos de presentes, além de cancelar a devolução. | Sim | Sim | Sim | Sim\*\* | Não |
| 802 | Contagem de Estoque | Esta operação permite ao usuário criar ou modificar diários de contagem de estoque para estoque físico ou contagens cíclicas. | Sim | Sim | Sim | Não | Não |
| 401 | Submenu | Estas operação leva o usuário a outra grade de botões vinculados. | Sim | Sim | Sim | Sim | Não |
| 1054 | Suspender turno | Suspender o turno atual, de modo que um turno novo ou diferente possa ser ativado no registro atual. | Sim | Sim | Sim | Não | Não |
| 503 | Suspender transação | Suspender a transação de vendas atual, de modo que ela possa ser chamada novamente mais tarde na loja. | Sim | Sim | Não | Sim‡ | Não |
| 1004 | Gravador de Tarefas | Abrir o Gravador de tarefas para registrar etapas processuais no PDV. | Não | Não | Não | Sim | Não |
| 1052 | Declaração de meios de pagamento | Esta operação permite ao usuário especificar a quantidade de dinheiro na gaveta para cada método de pagamento contado. | Sim | Sim | Sim | Sim | Não |
| 1210 | Remoção de Meio de Pagamento | Esta operação permite que o usuário remova dinheiro da gaveta ou turno atual. | Sim | Sim | Sim | Sim | Não |
| 920 | Relógio de ponto | Esta operação permite aos usuários perfurar cartões de ponto na entrada e saída de turnos ou pausas de trabalho. | Sim | Sim | Sim | Não | Não |
| 302 | Valor do Desconto Total | Inserir um valor de desconto para a transação. Essa operação se aplica apenas a itens com descontos e somente nos limites de desconto especificados. | Sim | Sim | Não | Sim | Não |
| 303 | Percentual total de desconto | Inserir um percentual de desconto para a transação. Essa operação se aplica apenas a itens com descontos e somente nos limites de desconto especificados. | Sim | Sim | Não | Sim | Não |
| 501 | Comentário da Transação | Adicionar um comentário à transação atual. | Sim | Sim | Não | Sim | Não |
| 922 | Exibir detalhes do produto | Abrir a página de detalhes do produto para o item de linha selecionado no momento. | Sim | Sim | Não | Sim | Não |
| 1003 | Exibir relatórios | Mostrar os relatórios que foram configurados para o usuário atual. | Sim | Sim | Sim | Não | Não |
| 921 | Exibir entradas do relógio de ponto | Mostrar as entradas do relógio de ponto para todos os funcionários na loja. | Sim | Sim | Sim | Não | Não |
| 211 | Pagamento Anulado | Anular a linha de pagamento selecionada no momento da transação. | Sim | Sim | Não | Sim | Não |
| 102 | Anular produto | Anular o item de linha de pagamento selecionado no momento da transação. | Sim | Sim | Não | Sim | Não |
| 500 | Anular transação | Anular a transação atual. | Sim | Sim | Não | Sim | Não |
| 916 | Windows workflow foundation | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Não |
| 924 | Leitura X de cartões bancários | Esta operação não tem suporte. | Não Aplicável | Não Aplicável | Não Aplicável | Não Aplicável | Sim |
| 311 | Remover descontos do sistema de transações | Remova todos os descontos aplicados pelo sistema, incluindo descontos baseados em cupom, da transação. Isso não remove descontos manuais. | Sim | Sim | Sim | Sim | Não |
| 312 | Reaplicar descontos do sistema | Reaplique os descontos do sistema na transação, caso tenham sido removidos usando a operação **Remover descontos do sistema da transação**. | Sim | Sim | Sim | Sim | Não |

\* A operação está disponível apenas em modo offline quando uma ordem ou uma cotação de venda de clientes está sendo criada, e somente se a criação offline de ordens e cotações de venda do cliente está configurada no perfil de funcionalidade do PDV. A operação não pode ser realizada quando as ordens são criadas usando o serviço em tempo real, ou quando as ordens são canceladas ou editadas.

† A operação pode ser executada apenas em modo offline quando o PDV é configurado para permitir a criação offline de clientes no perfil de funcionalidade PDV.

‡ Quando o PDV está offline, as transações suspensas podem ser canceladas apenas do banco de dados offline do registro atual. Os usuários não podem suspender e cancelar transações em registros.

§ Quando o PDV está offline, apenas as transações no banco de dados offline atual podem ser chamadas para devolução.

\*\* Quando o PDV está offline, apenas as transações no banco de dados de canal offline atual são mostradas no diário.
