---
title: Criar e trabalhar com campos personalizados
description: Este artigo mostra como criar campos personalizados por meio da interface do usuário para adequar o aplicativo à sua empresa.
author: jasongre
ms.date: 12/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysCustomFieldManageFields
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-1-31
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 18e7e8525352e8fdc397621c381ed4297837e30c
ms.sourcegitcommit: 69d7dd6a2d0dc7f2661c7d1f61e8874c7bde1448
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887278"
---
# <a name="create-and-work-with-custom-fields"></a>Criar e trabalhar com campos personalizados

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Embora haja um conjunto extensivo de campos predefinidos para gerenciar uma ampla variedade de processos empresariais, às vezes uma empresa precisa rastrear informações adicionais no sistema. Embora seja possível usar programadores para adicionar esses campos como extensões nas ferramentas de desenvolvedor, o recurso de campos personalizados permite que os campos sejam adicionados diretamente da interface de usuário, permitindo, dessa forma, adequar o aplicativo à sua empresa usando o navegador da Web.

*Somente os usuários com permissões especiais têm acesso a esse recurso.*

Este vídeo mostra como é fácil adicionar um campo personalizado a uma página: [Como adicionar campos personalizados](https://www.youtube.com/watch?v=gWSGZI9Vtnc).

## <a name="creating-custom-fields"></a>Criando campos personalizados

Depois de identificar as informações adicionais a serem rastreadas no aplicativo, você poderá criar o campo personalizado na tabela apropriada e mostrar esse novo campo em uma página.

As etapas a seguir descrevem o processo para criar um campo personalizado e colocá-lo em uma página.

1. Navegue até a página onde o novo campo é necessário.
2. Como a meta final é expor o campo personalizado em um formulário, o ponto de entrada para criar campos personalizados existe na experiência de personalização. Abra a barra de ferramentas de personalização selecionando **Opções** e, em seguida, **Personalizar este formulário**.
3. Clique em **Inserir** e, em seguida, em **Campo**.
4. Selecione a região do formulário onde deseja expor o novo campo. Após a seleção, a caixa de diálogo **Inserir campos** exibirá uma lista dos campos existentes que podem ser inseridos na região selecionada da página.
5. Verifique se o campo do seu interesse já existe na lista. Se estiver, você poderá simplesmente selecionar esse campo na lista e clicar em **Inserir**.
6. Clique no botão **Criar novo campo** acima da lista para iniciar o processo de criação de um campo personalizado. Isso abrirá a caixa de diálogo **Criar novo campo**.

    Se o botão **Criar novo campo** não aparece, você não tem as permissões necessárias para usar esse recurso.

7. Na caixa de diálogo **Criar novo campo**, insira as seguintes informações.
   
    1. Selecione a tabela de banco de dados onde esse campo deve ser adicionado. Observe que apenas as tabelas que oferecem suporte a campos personalizados aparecerão na lista suspensa. Consulte a seção abaixo para obter detalhes técnicos sobre tabelas com suporte.

    2. Selecione o tipo de dados do novo campo. Os tipos de dados disponíveis são caixa de seleção, data, data e hora, decimal, número, lista de separação e texto.

        - Se escolher o tipo de dados de texto, você também poderá especificar o tamanho máximo do texto que pode ser inserido nesse campo.
        - Se escolher o tipo de dados de lista de separação, você também poderá selecionar o conjunto de valores válidos para o campo.

    3. Forneça um nome, um rótulo e um texto de ajuda para o campo. O nome corresponde ao nome de campo físico no banco de dados, enquanto o rótulo e o texto de ajuda são o texto usado para representar esse campo na interface do usuário.

8. Se esse for o único campo que você precisa criar para esta página, clique em **Salvar**. Se precisar criar campos adicionais, clique em **Salvar e novo** e volte para a etapa 7. 

>[!Note] 
> Atualmente há um limite de **20 campos personalizados por tabela**.

9. Ao deixar a caixa de diálogo **Criar novo campo**, você retornará à caixa de diálogo **Inserir campos**. Todos os campos personalizados adicionados recentemente serão marcados automaticamente na lista de campos a ser inserida na página.
10. Clique em **Inserir** para adicionar os campos marcados na região selecionada da página.
11. **Opcional:** habilite o modo **Mover** da barra de ferramentas de personalização para mover os novos campos à localização desejada na região selecionada. Consulte [Personalizar a experiência do usuário](personalize-user-experience.md) para obter mais informações sobre como usar os diversos recursos de personalização para otimizar um formulário para seu uso pessoal.

> [!WARNING]
> A capacidade de inserir valores em um campo personalizado adicionado a uma página depende se a tabela associada ao campo personalizado é editável ou somente leitura. Quando a tabela associada é somente leitura, todos os campos vinculados a essa tabela, incluindo qualquer campo personalizado, também serão somente leitura.


## <a name="sharing-custom-fields-with-other-users"></a>Compartilhando campos personalizados com outros usuários

Após criar um campo personalizado e mostrá-lo em uma página, convém fornecer essa exibição de página com o novo campo a outros usuários no sistema. Isso pode ser realizado de duas formas usando os recursos de personalização do produto:

- O caminho recomendado é **publicar uma [exibição salva](saved-views.md)** com o campo personalizado adicionado à página para o conjunto apropriado de usuários. Se o recurso de exibições salvas não estiver habilitado, o administrador do sistema pode aplicar a personalização aos usuários desejados a partir da página **Personalização**. Para obter mais informações, consulte [Personalizar a experiência do usuário](personalize-user-experience.md).
- Como alternativa, você pode exportar as alterações (chamadas *personalizações*), enviá-las a um ou mais usuários e fazer com que cada um deles importe as alterações. A opção **Gerenciar** na barra de ferramentas de personalização permite exportar e importar personalizações.

## <a name="managing-custom-fields"></a>Gerenciando campos personalizados

O gerenciamento de todos os campos personalizados pode ser realizado por meio da página **Campos personalizados** no módulo de administração do sistema. Essa página permite que os usuários acessem muitos recursos, incluindo:

- Exibição de uma lista de todos os campos personalizados no sistema.
- Edição limitada de campos personalizados existentes.
- Exclusão de campos personalizados.
- Exposição de campos personalizados em entidades de dados.
- Fornecimento de traduções de rótulos e texto de ajuda de campos personalizados.

### <a name="viewing-all-custom-fields"></a>Exibição de todos os campos personalizados

A página **Campos personalizados** fornece visibilidade a todos os campos personalizados definidos no sistema. Selecione a tabela de seu interesse, e a página atualizará para mostrar a lista dos campos personalizados associados a essa tabela. Escolher um campo personalizado da lista permitirá que você exiba todos os detalhes do campo.

### <a name="editing-custom-fields"></a>Editando campos personalizados

Depois que um campo personalizado for criado, somente determinadas informações sobre ele poderão ser modificadas na página **Campos personalizados**.

Você *pode* modificar estes atributos:

- Etiqueta
- Texto de ajuda
- Comprimento, para campos de texto

Você *não pode* editar os atributos a seguir:

- Nome do campo
- Tipo de dados

Além disso, para campos de lista de separação, o conjunto de valores válidos para o campo personalizado pode ser reordenado e novos valores podem ser adicionados; entretanto, não é possível remover os valores existentes para o campo de lista de separação. Clique em **Aplicar alterações** quando terminar de editar os campos de uma tabela específica para que as alterações sejam salvas.

### <a name="exposing-custom-fields-on-data-entities"></a>Expondo campos personalizados em entidades de dados

Também pode ser importante permitir que campos personalizados estejam visíveis em entidades de dados. As entidades de dados são usadas no recurso [Visão geral da integração do Office](../../dev-itpro/office-integration/office-integration.md) e para cenários de importação/exportação de dados.

Siga estas etapas para expor um campo personalizado em uma entidade de dados:

1. Selecione o campo personalizado na página **Campos personalizados**.
2. Expanda a seção **Entidades** para exibir o conjunto de entidades relevantes.
3. Clique no botão **Editar**.
4. Modifique o campo **Habilitado** para que seja selecionado para cada entidade que deve expor este campo.
5. Clique em **Aplicar alterações** para salvar as seleções.

### <a name="allowing-custom-fields-to-be-displayed-in-other-languages"></a>Permitindo que os campos personalizados sejam exibidos em outros idiomas

Como os campos personalizados podem precisar ser acessados por usuários em vários idiomas, a página **Campos personalizados** fornece um mecanismo para permitir que o rótulo e o texto de ajuda de um campo personalizado possam ser traduzidos para outros idiomas.

As etapas a seguir descrevem o processo de tradução de campos personalizados para outros idiomas:

1. Selecione o campo personalizado na página **Campos personalizados**.
2. Selecione o botão **Traduções** no Painel de Ação. Isso abrirá um menu suspenso com traduções existentes para esse campo.
3. O menu suspenso **Idioma** mostra o conjunto de idiomas para os quais já foram fornecidas traduções.

    Se desejar editar uma tradução existente, selecione o idioma no menu e modifique os valores para o rótulo e o texto de ajuda.

    Caso contrário, clique no botão **Adicionar idioma**, selecione o idioma desejado no menu e, em seguida, forneça valores traduzidos para o rótulo e o texto de ajuda.

4. Clique em **OK** quando tiver terminado.

### <a name="deleting-custom-fields"></a>Excluindo campos personalizados

Quando você decidir que não precisa mais de um campo personalizado, um administrador do sistema poderá excluir o campo da página **Campos personalizados**. Para excluir um campo personalizado, selecione-o e clique em **Excluir**, clique em **Sim** para confirmar o processo e, por fim, clique em **Aplicar alterações**.

> [!NOTE]
> Essa ação não poderá ser desfeita e fará com que os dados associados ao campo sejam excluídos permanentemente do banco de dados.

## <a name="appendix"></a>Anexo

### <a name="why-cant-i-enter-a-value-in-my-custom-field"></a>Por que não consigo inserir um valor no meu campo personalizado? 

Se você não conseguir digitar um valor no campo personalizado quando a página estiver no modo **Editar**, pode ser porque a tabela à qual o campo foi adicionado é atualmente somente leitura. Todos os campos em uma tabela se tornam somente leitura se a tabela de apoio estiver atualmente configurada como somente leitura na página.   

### <a name="who-can-create-custom-fields"></a>Quem pode criar campos personalizados?

Apenas os administradores do sistema podem criar campos personalizados por padrão. No entanto, os usuários avançados que a organização julgar necessários poderão receber direitos para criar campos personalizados por um administrador do sistema usando a função de segurança **Usuário avançado de personalização de tempo de execução**. Os usuários sem essa função de segurança não poderão criar campos personalizados, mas ainda poderão ver e interagir com os campos personalizados adicionados por outros usuários no sistema.

### <a name="what-tables-support-custom-fields"></a>Que tabelas oferecem suporte a campos personalizados?

Por motivos técnicos e de desempenho, apenas as tabelas que atendem às seguintes condições atualmente permitem que os campos personalizados sejam adicionados.

- A tabela deve estar marcada como um destes grupos:

    - Agrupar
    - WorksheetHeader
    - Principal
    - Diversos
    - Parâmetro
    - Referência
    - TransactionHeader

- A tabela não pode estender outra tabela.
- A tabela não pode ser marcada como uma tabela do sistema.
- A tabela não pode ser temporária.

### <a name="can-i-reference-custom-fields-from-the-developer-tools"></a>Posso fazer referência a campos personalizados usando as ferramentas de desenvolvedor?  

Os campos personalizados podem ser gerenciados somente por meio da interface do usuário e não podem ser referenciados por código. 

### <a name="how-can-i-move-custom-fields-between-environments"></a>Como posso mover os campos personalizados entre os ambientes? 

A recomendação atual para mover campos personalizados entre ambientes é recriá-los manualmente no ambiente de destino. Para ver a lista completa de campos personalizados em uma determinada tabela:
1. Vá para a página **Campos personalizados** e selecione a tabela na lista suspensa. 
2. No ambiente de destino, siga o processo descrito anteriormente neste artigo para recriar cada campo. 
3. Depois de criar todos os campos, clique em **Aplicar alterações**.  
4. Mova todas as personalizações que contêm campos personalizados ao exportá-las do ambiente original e importá-las para o ambiente de destino.  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
