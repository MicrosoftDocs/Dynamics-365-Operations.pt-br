---
title: Limitar o uso de token de pagamento
description: Este artigo descreve o recurso que limita a forma de usar os tokens de pagamento no Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/20/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: 8092ab0724f33f21759aa84d25e0bdcb5b2ad5dd
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709642"
---
# <a name="limit-payment-token-usage"></a>Limitar o uso de token de pagamento

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Este artigo descreve o recurso que limita a forma de usar os tokens de pagamento no Microsoft Dynamics 365 Commerce. O uso de tokens é restrito ao escopo de um pedido de venda ou, se o cliente der o consentimento, é armazenado como um cartão registrado.

## <a name="key-terms"></a>Condições principais

| Termo | Descrição |
|---|---|
| Token | Um blob XML de referência no sistema do Dynamics 365 que armazena referências de pagamentos para fins transacionais. |
| Cartão registrado | Um token de referência de cartão salvo que é agregado para uso futuro no sistema do Dynamics 365 ou gateway de pagamento e que é exclusivo para a conta de um cliente. |

Os limites de uso do token de pagamento se aplicam a qualquer ambiente que use um serviço de gateway em que os tokens recorrentes são empregados. O [Dynamics 365 Payment Connector para Adyen](adyen-connector.md) de uso imediato utiliza tokens de pagamento recorrentes para realizar pedidos subsequentes, como ajustes de autorização e novas autorizações.

Para ajudar a controlar como esses tokens de pagamentos recorrentes são usados por todo o sistema, o recurso **Restringir uso do Token de Pagamento no Contexto da ordem** restringe o uso de um token recorrente para o escopo de um pedido de venda no sistema. Quando ele está desabilitado, o recurso modifica a interface de usuário (UI) do Commerce headquarters atualizando as páginas de entrada de pagamento e limitando a capacidade de selecionar referências anteriores de clientes para uso em novas instâncias de transações.

Esse recurso ajuda a respeitar as regras de uso de alguns emissores de pagamento, como a Visa. Nas [Regras Principais da Visa e Regras de Produtos e Serviços da Visa](https://usa.visa.com/content/dam/VCOM/download/about-visa/visa-rules-public.pdf), a Visa especifica que o uso de tokens de pagamento devem ficar restritos ao escopo de uma transação, a menos que o proprietário do cartão defina o contrário.

O recurso **Restringir uso do Token de Pagamento no Contexto da ordem** é relevante se você estiver usando um serviço de gateway de pagamento que emprega referências de tokens de pagamentos recorrentes.

## <a name="enable-the-feature"></a>Habilitar o recurso

Para habilitar o recurso **Restringir uso do Token de Pagamento no Contexto da ordem**, no Commerce headquarters do seu ambiente, acesse **Espaços de trabalho \> Gerenciamento de recursos**, encontre e selecione **Restringir uso do Token de Pagamento no Contexto da ordem** na lista e escolha **Habilitar Agora**.

## <a name="limit-payment-token-usage"></a>Limitar o uso de token de pagamento

Quando o recurso está desabilitado, as páginas do Commerce headquarters que são usadas para captura de forma de pagamento atualiza a forma como fazem referência às formas de pagamento do cliente que estão no arquivo desse cliente. Essa atualização vai afetar principalmente duas áreas de operação:

- Como um cartão registrado é inserido em nome de um cliente
- Como as informações de pagamento de um cliente são armazenadas para futuras entradas de pagamento de pedido de venda

Quando um cliente realiza uma transação nos canais do Commerce, os detalhes de pagamento são armazenados com um contexto de pedido de venda. Esse contexto limita o token de pagamento para que não seja usado como uma referência do registro do cliente nas páginas de pagamento para pedidos de venda novos ou editados no Commerce headquarters.

### <a name="payment-form-changes"></a>Mudanças da forma de pagamento

Quando um usuário de call center ou do Commerce headquarters recebe o pagamento de alguém com um pedido de venda, a página do pagamento mostra os detalhes da seleção da forma de pagamento. Quando o recurso **Restringir uso do Token de Pagamento no Contexto da ordem** está habilitado e um usuário seleciona o sinal de adição (**+**) na página de pagamento, apenas os registros "cartão registrado" são exibidos. As mudanças exigem que o usuário do Commerce headquarters ou call center insira todos os detalhes do pagamento que o cliente forneceu quando preencheu a página **Inserir informações de pagamento do cliente** da nova transação com pedido de venda.

A lista de valores do campo **Número** inclui apenas referências do cartão que estão associadas ao cliente proprietário do cartão registrado. Ele filtra qualquer referência anterior fora do escopo de um pedido de venda.

O sinal de adição (**+**) no campo **Número** fica disponível e pode ser usado para inserir as informações de pagamento que o cliente forneceu para a transação que está associada ao pedido de venda em processamento.

### <a name="how-cards-on-file-work"></a>Como os cartões registrados funcionam

Quando o recurso **Restringir uso do Token de Pagamento no Contexto da ordem** está habilitado, o cartão registrado é um token de pagamento salvo no registro do cliente e não é limitado ao escopo de um pedido de venda. Esses cartões permitem a associação rápida a usuários do Commerce headquarters quando eles preenchem a página de pagamento de um novo pedido de venda. Essa referência de token se aplica apenas ao ambiente do Dynamics 365. Para canais on-line que usam um serviço de gateway de pagamento que permite aos usuários salvar uma forma de pagamento para uso futuro no módulo iFrame, o gateway armazena de forma segura essas referências como uma ocorrência separada no cartão registrado do Dynamics 365.

Por exemplo, se o Dynamics 365 Commerce Payment Connector para Adyen for usado em um canal on-line, os clientes que inserirem as informações de cartão de crédito no módulo de pagamento iFrame veem apenas as referências do cartão salvo no serviço de gateway para a próxima compra on-line quando forem autenticados. Eles não veem que o ambiente do Dynamics 365 armazenou o cartão como uma opção no módulo de pagamento iFrame. De forma semelhante, quando compradores fazem um pedido por meio do call center, as referências on-line salvas do cartão não são exibidas como opções. O usuário do call center vê apenas cartões que foram registrados anteriormente no sistema do Dynamics 365 (como aceito pelo cliente) para salvar e usar em pedidos futuros.

Os usuários do Commerce headquarters podem salvar um cartão registrado de um cliente em **Varejo e Comércio \> Clientes** e selecionar o registro da conta do cliente. Na seção **Cliente \> Configurar**, os usuários que têm permissão para processar as páginas de pagamento podem usar a página de entrada **Cartões de crédito** para inserir um cartão de pagamento que será armazenado para futuras transações. Essa operação ajuda a economizar tempo quando futuros pagamentos de pedidos de venda forem processados para o cliente. Os usuários de call center e do Commerce headquarters poderão inserir os detalhes do cartão registrado apenas se o cliente concordar em usar a referência do cartão em futuras transações.

A caixa de seleção **Salvar para uso futuro** na parte inferior das páginas de pagamento do Commerce headquarters permitem que os usuários salvem o cartão para uso futuro. Essa caixa de seleção só deve ser usada se o cliente concordar em usar o cartão para transações futuras. Você pode mostrar ou restringir a caixa de seleção **Salvar para uso futuro** com a opção **Permitir cartão registrado do cliente** na guia **Pagamento** da página **Parâmetros do call center** no Commerce headquarters. Quando essa opção está definida como **Sim**, os usuários do Commerce headquarters que têm permissão para processar as páginas de pagamento podem salvar um cartão registrado selecionando a caixa **Salvar para uso futuro**. Quando essa opção está definida como **Não**, a caixa não fica disponível para os usuários do Commerce headquarters que têm permissão para processar as páginas de pagamento. A opção **Permitir cartão registrado do cliente** pode ser usada quando sua empresa quer restringir o uso de tokens recorrentes no Commerce headquarters, mas ainda não quer permitir que um cartão registrado seja salvo sem um procedimento para garantir que o cliente dê seu consentimento.

### <a name="commerce-headquarters-pages-where-the-recurring-token-restrictions-are-enforced"></a>As páginas do Commerce headquarters em que as restrições de tokens recorrentes são aplicadas

O escopo de restrição de tokens afeta as seguintes áreas no Commerce headquarters quando o recurso está habilitado:

- Informações de pagamento do cliente em **Pedido de venda \> Pagamentos \> Inserir pagamento do cliente**
- Ordens de continuidade
- Pagamentos de prestações
- Pagamentos de cartão de crédito das contas a receber

### <a name="manage-payment-tokens-archiving-or-removal"></a>Gerenciar tokens de pagamento (registro ou remoção)

Os tokens de pagamento que foram criados antes de o sinalizador do recurso **Restringir uso do Token de Pagamento no Contexto da ordem** ser habilitado (ou enquanto o recurso estava desabilitado) permanecem "fora do escopo" no sistema e podem aparecer nas listas de seleção na página de pagamento do Commerce headquarters. Esses tokens podem ser removidos regularmente de duas formas no Commerce headquarters:

- Use a página **Arquivar dados de transação de cartão** para configurar um trabalho que limpa ou registra os tokens de pagamento. Se você definir a opção **Excluir dados sem registrar** como **Sim**, os tokens que atendem à configuração **Idade mínima da transação (em dias)** serão excluídos. Para mais informações, consulte [Registrar dados de transação do cartão de crédito](archive-cc-data.md).
- Use a nova página **Limpar tokens de cartão de crédito** (**Contas a receber \> Consultas e relatórios \> Limpar \> Limpar tokens de cartão de crédito**), que permitem que você configure um trabalho em lote que exclui os tokens de pagamento. Defina os seguintes parâmetros:

    - O valor da **Idade mínima do token em dias** precisa ser de 90 dias ou mais.
    - As configurações de **Executar em segundo plano** podem ser usadas para definir as configurações de **Recorrência** ou **Alertas**.
    - É possível atribuir a execução da tarefa a um grupo em lote específico.
    - Se a opção **Privado** estiver definida como **Sim**, apenas o usuário que cria o trabalho pode executá-lo.
    - Uma configuração **Sim** da opção **Trabalho crítico** garante que o sistema acompanhe ativamente o status do trabalho.

Os tokens excluídos não podem ser recuperados. Defina o campo **Idade mínima do token em dias** considerando o intervalo adequado ao período de transação mais longo do seu ambiente (da autorização até a finalização ou reembolso).

## <a name="additional-resources"></a>Recursos adicionais

[Perguntas frequentes sobre pagamentos](payments-retail.md)

[Módulo de finalização da compra](../add-checkout-module.md)

[Módulo de pagamento](../payment-module.md)
