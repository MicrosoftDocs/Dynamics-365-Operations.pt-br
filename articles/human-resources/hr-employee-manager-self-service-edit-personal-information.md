---
title: Editar informações pessoais
description: Este artigo descreve como editar informações pessoais no autoatendimento para Funcionários e Gerentes.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d7e78873d0995334ac80ac22e8058b7fe0bc31ac
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686099"
---
# <a name="edit-personal-information"></a>Editar informações pessoais


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Você pode editar suas informações pessoais no Dynamics 365 Human Resources no espaço de trabalho **Autoatendimento para funcionários**.

As informações pessoais que você pode editar incluem:

- Endereços
- Detalhes do Contato
- Contatos pessoais
- Números de identificação
- Forma de pagamento
- Imagem usada no Human Resources

>[!NOTE]
>Talvez não seja possível editar certos tipos de informações pessoais, como detalhes do contato comercial. Para obter mais informações, consulte [Restringir a edição de informações pessoais](hr-employee-self-service-restrict-editing.md).

Os parâmetros definidos na página **Parâmetros de catálogo de endereços global** determinam quais funções podem ver suas informações pessoais.

1. No Human Resources, selecione **Autoatendimento para funcionários**.

2. Selecione **Editar detalhes pessoais**.

3. Para alterar seu endereço, selecione a guia **Endereços**. As alterações que você faz aparecem no espaço de trabalho **Gerenciamento de equipe** para alertar o HR.

    - Para adicionar um novo endereço, selecione **Adicionar**.
    - Para editar um endereço existente, selecione o endereço e selecione **Editar**.
    - Para exibir um mapa, selecione **Mapa**.
    - Para adicionar ou remover um contato, selecione **Mais opções** e, em seguida, selecione **Avançado**. Em **Informações de contato**, selecione **Adicionar** ou **Remover** e edite os campos conforme necessário.
    - Para definir seu fuso horário e local, selecione **Mais opções** e escolha **Avançado**. Em **Geral**, edite os campos conforme necessário.

4. Para alterar seus detalhes de contato, selecione a guia **Detalhes do contato**. Você pode fornecer diferentes tipos de informações de contato, incluindo telefone, email e links de redes sociais. Você pode definir um detalhe do contato como principal, mas apenas um de cada tipo como principal.

    - Para adicionar novas informações de contato, selecione **Adicionar**. Edite os campos conforme necessário.
    - Para editar as informações de contato existentes, selecione o item e selecione **Editar**. Edite os campos conforme necessário.
    - Para definir um detalhe do contato como privado, selecione o item, selecione **Avançado** e defina a opção **Privado** como **Sim**. Selecione **OK**.
      >[!NOTE]
      >O botão **Avançado** não estará disponível se o administrador tiver habilitado o recurso **(Versão preliminar) Restringir a adição ou edição de endereço e de informações de contato por funcionários para fins de seleção** no seu ambiente. Para obter mais informações, consulte [Restringir a edição de informações pessoais](hr-employee-self-service-restrict-editing.md).
  
5. Para alterar seus contatos pessoais, selecione a guia **Contatos pessoais**. Você pode designar contatos de emergência, beneficiários e dependentes. Um contato pode ser uma pessoa ou organização. O recurso **Gerenciamento de benefícios** usa informações de contato pessoais. Para obter mais informações, consulte [Configurar opções de qualificação para contato pessoal](hr-benefits-setup-contact-eligibility-options.md).

6. Para alterar seus números de identificação, como CPF (Cadastro de Pessoas Físicas), selecione a guia **Números de identificação**. As alterações podem passar por um processo de aprovação se sua organização configurar um fluxo de trabalho de aprovação.

    - Para adicionar um número de identificação, selecione **Novo**. Preencha os campos conforme necessário e selecione **Salvar**.
    - Para editar um número, selecione **Editar**. Editar os campos conforme necessário e selecione **Salvar**.

7. Para alterar os métodos pelos quais você é pago, selecione a guia **Minhas informações de pagamento**. Essa guia estará disponível apenas se os métodos de pagamento estiverem habilitadas na página **Parâmetros do Human Resources**. O HR pode habilitar **Boleto bancário**, **Pagamento à vista**, **Cheque**, **Pagamento eletrônico** ou **Outro**. O HR também pode desabilitar a validação de pagamento eletrônico (usado para a folha de pagamento dos EUA) e a validação de conta bancária e número de roteamento.

8. Para alterar a imagem exibida no Human Resources do seu perfil, selecione a guia **Imagem**. Dependendo das configurações da sua organização, as imagens podem ser roteadas para aprovação.

    - Para carregar uma imagem, selecione **Carregar nova imagem**.
    - Para remover uma imagem, selecione a imagem e selecione **Remover**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
