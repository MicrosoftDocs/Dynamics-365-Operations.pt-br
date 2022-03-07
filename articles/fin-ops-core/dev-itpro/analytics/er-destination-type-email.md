---
title: Tipo de destino de ER do email
description: Este tópico explica como configurar um destino de email para cada componente de PASTA ou ARQUIVO de um formato de relatório eletrônico (ER).
author: NickSelin
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: dc89e7ff43e5df358f6d41bd295e981c883085bc
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2021
ms.locfileid: "7595194"
---
# <a name="email-er-destination-type"></a>Tipo de destino de ER do email

[!include [banner](../includes/banner.md)]

Quando um formato ER (relatório eletrônico) é executado, um ou mais documentos de saída podem ser gerados. Os componentes de formato **Pasta** ou **Arquivo** pasta são usados nos formatos ER para especificar a estrutura dos documentos de saída. Você pode configurar um destino de email para esses tipos de componentes para enviar documentos de saída como anexos de email.

Você pode configurar um destino de email para cada **Pasta** **ou** componente de arquivo de um formato ER. Nesse caso, **cada documento de saída é enviado individualmente**. Com base na configuração de destino, um documento gerado é entregue como um anexo de um email. 

> [!NOTE]
> Se nenhum documento for gerado, como a expressão **Habilitada** para o componente **Arquivo** relevante foi configurada para retornar um valor **Booliano** falso, nenhum email será enviado, mesmo que um destino de email esteja configurado e habilitado para o componente.

Você também pode [agrupar](#grouping) vários componentes de **Pasta** ou **Arquivo** e configurar um destino de email para todos os componentes do grupo. Nesse caso, todos os documentos de saída gerados por componentes que pertencem ao grupo **são enviados como vários anexos de um único email**. Com base na configuração de destino, cada documento gerado é entregue como um anexo de um único email.

> [!NOTE]
> Se pelo menos um documento for gerado por um componente **Arquivo** em um grupo de componentes, um email será enviado. Se nenhum documento for gerado por componentes agrupados, como a expressão **Habilitada** para cada **Arquivo** relevante foi configurada para retornar um valor **Booliano** falso, nenhum email será enviado, mesmo que um destino de email esteja configurado e habilitado para o grupo de componentes.
>
> O **Email** é o único destino que pode ser configurado para um grupo de componentes. Para entregar um documento enviado por email com base na configuração de destino de email de um grupo, adicione mais um registro de destino, selecione o componente desejado e configure outro destino para esse registro.

Vários grupos de componentes podem ser configurados para uma única configuração de formato ER. Dessa forma, você pode configurar um destino de email para cada grupo de componentes e um destino de email para cada componente.

## <a name="enable-an-email-destination"></a>Habilitar um destino de email

Para enviar um ou mais arquivos de saída por email, siga estas etapas.

1. Na página **Destino do relatório eletrônico**, na FastTab **Destino do arquivo**, selecione um componente ou grupo de componentes na grade.
2. Selecione **Configurações** e, na caixa de diálogo **Configurações de destino**, na guia **Email**, defina a opção **Habilitado** como **Sim**.

[![Configurar a opção Habilitado como Sim para um destino de email.](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="configure-an-email-destination"></a>Configurar um destino de email

### <a name="email-content"></a>Conteúdo do email

Você pode editar o assunto e o corpo da mensagem de email.

No campo **Assunto**, insira o texto do assunto de email que deve aparecer no campo assunto de uma mensagem eletrônica que é gerada no tempo de execução. No campo **Assunto**, insira o texto do corpo do email que deve aparecer no campo do corpo de uma mensagem eletrônica. Você pode configurar um texto constante para o assunto e o corpo do email ou pode usar [fórmulas](er-formula-language.md) de ER para criar textos de email no tempo de execução. A fórmula configurada deve retornar um valor do tipo [String](er-formula-supported-data-types-primitive.md#string).

O corpo do seu email é composto no formato de TEXTO ou HTML, dependendo do cliente de email. Você pode usar qualquer layout, estilo e marca permitidos por HTML e CSS (Folhas de Estilos em Cascata).

> [!NOTE]
> Os clientes de email impõem limitações de estilo e layout que podem exigir ajustes no HTML e CSS que você usa para o corpo da mensagem. Recomendamos que você se familiarize com as práticas recomendadas para criar HTML que receberá suporte dos clientes de email mais conhecidos.
>
> Use a codificação correta para implementar um retorno de carro, dependendo da formatação do texto. Para obter mais informações, consulte a definição do tipo de dados [String](er-formula-supported-data-types-primitive.md#string).

### <a name="email-addresses"></a>Endereços de email

Você pode especificar o remetente e os destinatários do email. Por padrão, é enviado um email em nome do usuário atual. Para especificar outro remetente de email, você deve configurar o campo **De**.

> [!NOTE]
> Quando um destino de email é configurado, o campo **De** só fica visível para os usuários que têm o `ERFormatDestinationSenderEmailConfigure` privilégio de segurança **Configurar o endereço de email do remetente para destinos de formato ER**.
>
> Quando um destino de email é oferecido para modificação em [tempo de execução](electronic-reporting-destinations.md#security-considerations), o campo **De** só fica visível para os usuários que têm o `ERFormatDestinationSenderEmailMaintain` privilégio de segurança **Manter o endereço de email do remetente para o destino do formato ER**.
>
> Quando o campo **De** é configurado para usar um endereço de email diferente do do usuário atual, a permissão **Enviar como** ou **Enviar em nome de** deve ser [definida](/microsoft-365/solutions/allow-members-to-send-as-or-send-on-behalf-of-group) corretamente com antecedência. Do contrário, a exceção a seguir será gerada em tempo de execução: "Não é possível enviar email como \<from email account\> da conta \<current user account\>, verifique as permissões de 'Enviar como' em \<from email account\>".

Você pode configurar o campo **De** para retornar mais de um endereço de email. Nesse caso, o primeiro endereço na lista é usado como endereço do remetente do email.

Para especificar destinatários de email, você deve configurar os campos **Para** e **Cc** (opcional).

Você pode configurar endereços de email para o ER de duas formas. A configuração pode ser concluída da mesma forma que no recurso Gerenciamento de Impressão ou você pode resolver um endereço de email usando uma referência direta à configuração de ER por meio de uma fórmula.

## <a name="email-address-types"></a>Tipos de endereço de email

Se você selecionar **Editar** ao lado do campo **De**, **Para** ou **Cc** na caixa de diálogo **Configurações de destino**, será exibida a caixa de diálogo **Email de**, **Email para** ou **Email Cc** apropriada. Nela, você pode configurar o remetente e os destinatários do email. Selecione **Adicionar** o tipo de endereço de email para uso. No momento, dois tipos são suportados: **Email de gerenciamento de impressão** e **Email de configuração**.

[![Selecionar o tipo de endereço de email.](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management-email"></a>Imprimir email de gerenciamento

Se você selecionar **Email de gerenciamento de impressão** como o tipo de endereço de email, poderá inserir endereços de email fixos na caixa de diálogo **Email de**, **Email para** ou **Email Cc** definindo os seguintes campos:

- No campo **Origem de email**, selecione **Nenhum**.
- No campo **Endereços de email adicionais, separados por ";"**, insira os endereços de email fixos.

Uma alternativa é obter os endereços de email a partir dos detalhes do contato do grupo para as quais você quer gerar um documento de saída. Para usar os endereços de e-mail não fixos, no campo **Origem de mail** selecione a [função](../../fin-ops/organization-administration/overview-global-address-book.md#party-roles) do grupo para um destino de arquivo. As seguintes funções são suportadas:

- Cliente
- Fornecedor
- Cliente potencial
- Contato
- Concorrente
- Trabalhador
- Candidato
- Fornecedor potencial
- Fornecedor não permitido
- Pessoa jurídica em geral

Por exemplo, para configurar um destino de email para um formato ER usado para processar pagamentos de fornecedor, selecione a função **Fornecedor**.

Depois de selecionar a função desejada, selecione o botão **Vincular** (símbolo de corrente) ao lado do campo **Conta de origem de email** para abrir a página [Designer de fórmulas](general-electronic-reporting-formula-designer.md). Em seguida, você poderá usar esta página para configurar uma fórmula que retorne, no tempo de execução, o número da=e conta atribuído à função configurada do documento processado para o destino do email.

> [!NOTE]
> Fórmulas são específicas à configuração de ER.

Na página **Designer de fórmulas**, no campo **Fórmula**, insira uma referência específica de documento a uma função com suporte. Em vez de digitar a referência, no painel **Origem de dados**, localize e selecione o nó da fonte de dados que representa uma conta da função configurada e selecione **Adicionar origem de dados** para atualizar a fórmula. Por exemplo, se você configurar o destino de email para a configuração **Transferência de crédito ISO 20022** usada para processar pagamentos de fornecedor, o nó que representa uma conta de fornecedor é `'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

![Configurar uma conta de origem de email.](./media/er_destinations-emaildefineaddresssource.gif)

Se os números de conta da função configurada forem exclusivos para a instância inteira do Microsoft Dynamics 365 Finance, o campo **Empresa de origem de email** na caixa de diálogo **Email para** poderá permanecer em branco.

Como alternativa, você pode ter uma situação em que diferentes partes do [Catálogo de endereços global](../../fin-ops/organization-administration/overview-global-address-book.md) tenham sido registradas em diferentes ([entidades legais](../../fin-ops/organization-administration/organizations-organizational-hierarchies.md#legal-entities) de empresas) de tal forma que todas usem o mesmo número de conta para preencher a função configurada. Nesse caso, os números de conta para a função configurada não são exclusivos para toda a instância financeira. Portanto, para selecionar explicitamente um participante, você não pode especificar somente um número de conta. Você também deve especificar a empresa da qual o participante foi registrado no escopo para preencher a função configurada. Selecione o botão **Vincular** (símbolo de corrente) ao lado do campo **Conta de origem de email** na caixa de diálogo **Email para** para abrir a página [Designer de fórmulas](general-electronic-reporting-formula-designer.md). Em seguida, você pode usar esta página para configurar uma fórmula que retorne, no tempo de execução, o código da empresa da qual a origem desejada deve ser encontrada no escopo.

> [!TIP]
> Se você precisar usar o código da empresa para executar um formato ER, mas o formato ER não fornecer nenhuma fonte de dados da qual o código da empresa possa ser obtido, configure a fórmula `GetCurrentCompany()` usando a função ER [GETCURRENTCOMPANY](er-functions-other-getcurrentcompany.md).

> [!NOTE]
> Fórmulas são específicas à configuração de ER.

Para especificar o tipo de endereço de email que deve ser usado no tempo de execução, na caixa de diálogo **Email para**, selecione **Editar** ao lado do campo **Para** para abrir a caixa de diálogo **Atribuir endereço de email**. E então defina os campos a seguir:

- No campo **Finalidade**, selecione as finalidades do desejo. Serão usados somente os endereços de email das finalidades selecionadas de contatos do participante descoberto.
- Defina a opção **Contato principal** como **Sim** para usar um endereço de email configurado para o participante descoberto como o endereço de email principal.

> [!NOTE]
> Se as finalidades forem selecionadas no campo **Finalidade** e a opção **Contato principal** estiver definida como **Sim** ao mesmo tempo, todos os emails que satisfaçam pelo menos um critério configurado será usado no tempo de execução.

### <a name="configuration-email"></a>Email de configuração

Selecione **Configuração de email** como o tipo de endereço de email se a configuração usada tiver um nó nas fontes de dados que retorna um único endereço de email ou vários endereços de email separados por ponto-e-vírgula (;). Você pode usar [fontes de dados](general-electronic-reporting.md#FormatComponentOutbound) e [funções](er-formula-language.md#Functions) no designer de fórmulas para obter um endereço de email formatado corretamente ou endereços de email formatados corretamente, separados por ponto-e-vírgulas. Por exemplo, se você usar a configuração **Transferência de crédito ISO 20022**, o nó que representa o endereço de email principal de um fornecedor dos detalhes de contato do fornecedor para o qual a carta de material deve ser enviada é `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Configurar uma fonte de endereço de email.](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="group-format-components"></a><a id="grouping"></a>Componentes de formato de grupo

Para agrupar componentes de formato, na página **Destino do relatório eletrônico**, na FastTab **Destino do arquivo**, selecione os componentes na grade e, em seguida, selecione **Grupo**.

O **Email** é o único destino configurado anteriormente que ainda está disponível para os componentes selecionados. Nenhum outro destino configurado anteriormente está disponível, pois ele é considerado incompatível com um grupo de componentes. Você será notificado sobre essas alterações, conforme apropriado.

O registro adicionado anteriormente é considerado o cabeçalho de grupo criado. Esse registro de cabeçalho mantém as configurações de destino de email do grupo. Outros registros são membros do grupo que usarão as configurações de destino de email do registro de cabeçalho de grupo.

Para desagrupar componentes de formato, na FastTab **Destino do arquivo**, selecione um registro que pertença ao grupo e selecione **Desagrupar**.

- Se você selecionar um registro de cabeçalho, todo o grupo será desagrupado.
- Se você selecionar um registro de membro e for o último registro de membro de um grupo, todo o grupo será desagrupado.
- Se você selecionar um registro de membro que não seja o último registro de membro de um grupo, esse registro será excluído do grupo atual.

A ilustração a seguir mostra a estrutura de um formato ER configurado para produzir um arquivo de saída zipado que contém uma nota de carta de cobrança e faturas de cliente apropriadas no formato PDF.

[![Estrutura de um formato ER que gera documentos de saída.](./media/ER_Destinations-Email-Grouping1.png)](./media/ER_Destinations-Email-Grouping1.png)

A ilustração a seguir mostra o processo, conforme descrito neste tópico, agrupando componentes individuais e habilitando o destino **Email** para o novo grupo, de forma que uma nota de carta de cobrança seja enviada junto com as faturas de cliente apropriadas como anexos de email.

[![Agrupar componentes individuais e habilitar o destino do email.](./media/ER_Destinations-Email-Grouping2.gif)](./media/ER_Destinations-Email-Grouping2.gif)

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)
- [Destinos de Relatório eletrônico (ER)](electronic-reporting-destinations.md)
- [Designer de fórmulas no relatório eletrônico (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
