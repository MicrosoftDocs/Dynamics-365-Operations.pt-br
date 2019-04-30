---
title: Modelos de email
description: Este tópico fornece informações sobre os modelos de email que você pode criar e usar no Microsoft Dynamics 365 for Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: b88ba4386dbf3513d75990acca1c07fa6f0dc9b0
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "857051"
---
# <a name="email-templates"></a>Modelos de email
[!include[banner](../includes/banner.md)]

Usando a biblioteca de modelos de email, os administradores podem criar um tema uniforme e marcas para todos os emails enviados com o Microsoft Dynamics 365 for Talent: Attract. Os administradores também podem coletar um conjunto de modelos de conteúdo de email que outros usuários podem consumir. A equipe de contratação pode usar esses modelos no fluxo de trabalho para enviar emails com maior eficiência. Alguns emails do Attract são configurados para serem enviados automaticamente. O administrador pode usar a biblioteca de modelos de email para personalizar o conteúdo desses emails.

> [!NOTE]
> Para usar modelos de email, sua organização deve ter o complemento Contratação Abrangente.

## <a name="global-template-configurations"></a>Configurações do modelo global

Para criar marcas consistentes para todas as comunicações por email, o administrador deve primeiro definir o cabeçalho e rodapé globais para todos os modelos de email. No Centro de administração, na guia **Configurações de modelo de email**, na seção **Cabeçalho** , o administrador pode carregar uma imagem para usar como o cabeçalho ou a faixa para todos os emails. A imagem pode ser um logotipo da empresa, um timbre ou qualquer outra imagem representativa. É recomendável que a largura tenha entre 25 e 800 pixels e a altura entre 25 e 150 pixels, pois essas dimensões são ideais para a maioria dos clientes de email, como o Microsoft Outlook. A imagem deve ser um arquivo JPEG, JPG, PNG ou SVG. O tamanho do arquivo deve ser inferior a 1 megabyte (MB). Após uma imagem ser carregada, uma exibição do cabeçalho será gerada e mostrada. Se a imagem do cabeçalho precisar ser removida ou substituída, o administrador poderá usar a opção **Remover** acima da exibição.

Na seção **Rodapé**, o administrador pode fornecer links para a política de privacidade da empresa para comunicação, além dos termos e condições. Esses links são inseridos em um rodapé que é gerado automaticamente. Uma visualização deste rodapé é exibida.

Verifique se você salvou suas alterações antes de fechar o Centro de administração.

> [!NOTE] 
> O cabeçalho e o rodapé são configurações globais para todos os emails. Portanto, eles aparecerão em todos os emails enviados por meio do Attract. Se as configurações não estiverem definidas, o cabeçalho e o rodapé serão deixados fora de todos os emails.

## <a name="email-template-library"></a>Biblioteca de modelos de email 

Após a definição das configurações de modelo global, o administrador poderá começar a criar e coletar modelos de todos os emails enviados do Attract. A biblioteca de modelos de email está disponível apenas para administradores. Para abrir a biblioteca, no menu principal de navegação, selecione guia **Modelos de email**. A biblioteca é categorizada pelas várias atividades no Attract para a quais os emails devem ser enviados, como agendamento, avaliação e criação de trabalhos. O administrador pode selecionar qualquer categoria para exibir todos os tipos de email associados à atividade. Por exemplo, selecione **Agendamento** para exibir os vários tipos de email que são enviados durante o processo de agendamento e todos os modelos disponíveis para cada tipo de email. Cada subseção em uma categoria representa um tipo de email.

Alguns tipos de email podem ter mais de um destinatário. Por exemplo, na categoria **Agendamento**, os emails enviados quando o resumo do agendamento de entrevista é necessário são enviados para candidatos e entrevistadores. Cada seção tem duas colunas principais: **Título do Modelo** e **Destinatário**. Cada linha em uma seção representa um único modelo para um tipo de email. Primeiro, um símbolo de cadeado aparecerá na linha para cada modelo. Esse símbolo indica que o modelo é o padrão fornecido com o Attract e que ele não pode ser excluído. Para qualquer modelo, o administrador pode usar o botão de reticências (**...**) para duplicar o modelo, defini-lo como um modelo padrão ou excluí-lo. Quando um modelo é definido como um modelo padrão, um de dois comportamentos pode ocorrer. O comportamento é indicado pelos selos que aparecem na linha do modelo:

- **Padrão** – Este selo indica que o modelo é o modelo padrão para o email que é enviado e essas informações serão inseridas nele quando um usuário enviar um email desse tipo específico.
- **Padrão** + **Enviado automaticamente** – esta combinação de selos indica que o modelo é o modelo ativo dos emails gerados pelo sistema que são enviados automaticamente.

Para editar um modelo, selecione a linha e faça alterações no modelo.

> [!NOTE]
> Cada destinatário de determinado tipo de email tem um modelo padrão. Todos os modelos padrão do Attract são definidos como modelos padrão até o administrador criar um novo modelo para um tipo específico de email e definir como o modelo padrão.

## <a name="create-a-template"></a>Criar um modelo

Para criar um modelo, no canto superior direito da biblioteca de modelos de email, selecione **+ Novo modelo**. Para selecionar o tipo de email para o qual você está criando o modelo, selecione o destinatário, o processo e o evento ao qual o email deve ser enviado. Depois, selecione **Criar**.

O modelo é aberto na exibição de edição e você pode nomear o modelo. Por exemplo, se o modelo destinar-se a candidatos de uma universidade norte-americana, mas o conteúdo for escrito em francês, você deverá digitar **University\_US\_Francais** como o título. O título, a linha de assunto e o conteúdo do corpo de qualquer modelo pode dar suporte a idiomas além do inglês.

O campo **Para** de um modelo não pode ser editado, pois você já selecionou o destinatário ao criar o modelo pela primeira vez.

Você pode adicionar personas como **Recrutador** ou **Gerente de contratação** à linha de cópia carbono (Cc). Quando o email for enviado, essas funções serão substituídas automaticamente pelos usuários apropriados, com base no contexto do trabalho.

A linha do assunto e o conteúdo do corpo dão suporte a espaços reservados. Você poderá inserir espaços reservados digitando **\#** e selecionando o espaço reservado apropriado na lista suspensa de preenchimento automático. A lista dos espaços reservados disponíveis aparece no lado direito da página. Quando o email for enviado, os espaços reservados serão substituídos automaticamente, com base no contexto do trabalho e no destinatário. Por exemplo, o modelo de um email que é enviado para candidatos contém o espaço reservado \#{Candidate\_Name}. Quando o email for enviado a um candidato chamado Cameron, esse espaço reservado será substituído pelo nome Cameron.

O editor de conteúdo do corpo é um editor de rich text que permite definir o estilo e o formato do texto. Ele também permite inserir hiperlinks e âncoras.

Após um modelo ser criado para um tipo específico de email, selecione o botão de reticências (**...**) na linha do modelo e defina-o como o modelo padrão.

## <a name="consume-templates"></a>Modelos de consumo

Quando a equipe de contratação envia um email, ela pode usar modelos criados pelo administrador. Se vários modelos tiverem sido criados para o email que um usuário estiver enviando, uma lista suspensa aparecerá no fluxo de trabalho de composição de email. O modelo padrão é inserido automaticamente, mas o usuário pode selecionar um modelo diferente.

> [!NOTE] 
> Para os emails que são enviados automaticamente, vários modelos podem ser criados. Porém, apenas um modelo pode ser definido como o modelo ativo. Como esse processo é disparado por eventos, somente o administrador pode determinar que modelo será usado, com base na combinação de selos **Padrão** e **Enviado automaticamente** na biblioteca de modelos.
