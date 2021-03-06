---
title: '方法: XAML でビューを使用してデータの並べ替えおよびグループ化を行う'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: 9e42dd330535f71438ab7af3dca9d078e9dfd8d3
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460117"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>方法: XAML でビューを使用してデータの並べ替えおよびグループ化を行う
この例では、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] でデータ コレクションのビューを作成する方法を示します。 ビューでは、グループ化、並べ替え、フィルター処理、現在の項目の概念などの機能を使用できます。  
  
## <a name="example"></a>例  
 次の例では、*places* という名前の静的リソースは *Place* オブジェクトのコレクションとして定義されており、各 *Place* オブジェクトは市の名前と州で構成されます。 プレフィックス *src* は、データソース *Places* が定義されている名前空間にマップされています。 プレフィックス *scm* は `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` にマップされ、*dat* は `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"` にマップされています。  
  
 次の例では、市の名前によって並べ替えられ、州でグループ化された、データ コレクションのビューを作成します。  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 その後、次の例のように、そのビューをバインディング ソースにすることができます。  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <xref:System.Windows.Data.XmlDataProvider> リソースで定義されている XML データへのバインディングでは、XML 名の前に @ 記号を付けます。  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Data.CollectionViewSource>
- [データ コレクションの既定のビューを取得する](how-to-get-the-default-view-of-a-data-collection.md)
- [データ バインディングの概要](../../../desktop-wpf/data/data-binding-overview.md)
- [方法トピック](data-binding-how-to-topics.md)
