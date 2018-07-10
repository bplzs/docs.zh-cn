---
title: C# 7.3 中的新增功能
description: C# 7.3 中的新增功能概述
ms.date: 05/16/2018
ms.openlocfilehash: 135351fa06a498e4aa90cb4d9372880b8119de0f
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106770"
---
# <a name="whats-new-in-c-73"></a><span data-ttu-id="cfd4a-103">C# 7.3 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="cfd4a-103">What's new in C# 7.3</span></span>

<span data-ttu-id="cfd4a-104">C# 7.3 版本有两个主要主题。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-104">There are two main themes to the C# 7.3 release.</span></span> <span data-ttu-id="cfd4a-105">第一个主题提供使安全代码的性能与不安全代码的性能一样好的功能。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-105">One theme provides features that enable safe code to be as performant as unsafe code.</span></span> <span data-ttu-id="cfd4a-106">第二个主题提供对现有功能的增量改进。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-106">The second theme provides incremental improvements to existing features.</span></span> <span data-ttu-id="cfd4a-107">此外，在此版本中添加了新的编译器选项。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-107">In addition, new compiler options were added in this release.</span></span>

<span data-ttu-id="cfd4a-108">以下新增功能支持使安全代码获得更好的性能的主题：</span><span class="sxs-lookup"><span data-stu-id="cfd4a-108">The following new features support the theme of better performance for safe code:</span></span>

- <span data-ttu-id="cfd4a-109">无需固定即可访问固定的字段。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-109">You can access fixed fields without pinning.</span></span>
- <span data-ttu-id="cfd4a-110">可以重新分配 `ref` 本地变量。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-110">You can reassign `ref` local variables.</span></span>
- <span data-ttu-id="cfd4a-111">可以使用 `stackalloc` 数组上的初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-111">You can use initializers on `stackalloc` arrays.</span></span>
- <span data-ttu-id="cfd4a-112">可以对支持模式的任何类型使用 `fixed` 语句。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-112">You can use `fixed` statements with any type that supports a pattern.</span></span>
- <span data-ttu-id="cfd4a-113">可以使用其他泛型约束。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-113">You can use additional generic constraints.</span></span>

<span data-ttu-id="cfd4a-114">对现有功能进行了以下增强：</span><span class="sxs-lookup"><span data-stu-id="cfd4a-114">The following enhancements were made to existing features:</span></span>

- <span data-ttu-id="cfd4a-115">可以使用元组类型测试 `==` 和 `!=`。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-115">You can test `==` and `!=` with tuple types.</span></span>
- <span data-ttu-id="cfd4a-116">可以在多个位置使用表达式变量。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-116">You can use expression variables in more locations.</span></span>
- <span data-ttu-id="cfd4a-117">可以将属性附加到自动实现的属性的支持字段。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-117">You may attach attributes to the backing field of auto-implemented properties.</span></span>
- <span data-ttu-id="cfd4a-118">由 `in` 区分的参数的方法解析得到了改进。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-118">Method resolution when arguments differ by `in` has been improved.</span></span>
- <span data-ttu-id="cfd4a-119">重载解析的多义情况现在变得更少。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-119">Overload resolution now has fewer ambiguous cases.</span></span>

<span data-ttu-id="cfd4a-120">新的编译器选项为：</span><span class="sxs-lookup"><span data-stu-id="cfd4a-120">The new compiler options are:</span></span>

- <span data-ttu-id="cfd4a-121">`-publicsign`，用于启用程序集的开放源代码软件 (OSS) 签名。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-121">`-publicsign` to enable Open Source Software (OSS) signing of assemblies.</span></span>
- <span data-ttu-id="cfd4a-122">`-pathmap`用于提供源目录的映射。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-122">`-pathmap` to provide a mapping for source directories.</span></span>

<span data-ttu-id="cfd4a-123">本文的剩余部分提供了详细信息和链接，以便你详细了解每项改进。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-123">The remainder of this article provides details and links to learn more about each of the improvements.</span></span>

## <a name="enabling-more-performant-safe-code"></a><span data-ttu-id="cfd4a-124">使用性能更好的安全代码</span><span class="sxs-lookup"><span data-stu-id="cfd4a-124">Enabling more performant safe code</span></span>

<span data-ttu-id="cfd4a-125">你应能够安全地编写性能与不安全代码一样好的 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-125">You should be able to write C# code safely that performs as well as unsafe code.</span></span> <span data-ttu-id="cfd4a-126">安全代码可避免错误类，例如缓冲区溢出、杂散指针和其他内存访问错误。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-126">Safe code avoids classes of errors, such as buffer overruns, stray pointers, and other memory access errors.</span></span> <span data-ttu-id="cfd4a-127">这些新功能扩展了可验证安全代码的功能。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-127">These new features expand the capabilities of verifiable safe code.</span></span> <span data-ttu-id="cfd4a-128">努力使用安全结构编写更多代码。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-128">Strive to write more of your code using safe constructs.</span></span> <span data-ttu-id="cfd4a-129">这些功能使其更容易实现。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-129">These features make that easier.</span></span>

### <a name="indexing-fixed-fields-does-not-require-pinning"></a><span data-ttu-id="cfd4a-130">索引 `fixed` 字段不需要进行固定</span><span class="sxs-lookup"><span data-stu-id="cfd4a-130">Indexing `fixed` fields does not require pinning</span></span>

<span data-ttu-id="cfd4a-131">请考虑此结构：</span><span class="sxs-lookup"><span data-stu-id="cfd4a-131">Consider this struct:</span></span>

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

<span data-ttu-id="cfd4a-132">在早期版本的 C# 中，需要固定变量才能访问属于 `myFixedField` 的整数之一。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-132">In earlier versions of C#, you needed to pin a variable to access one of the integers that are part of `myFixedField`.</span></span> <span data-ttu-id="cfd4a-133">现在，将在安全上下文中编译以下代码：</span><span class="sxs-lookup"><span data-stu-id="cfd4a-133">Now, the following code compiles in a safe context:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

<span data-ttu-id="cfd4a-134">变量 `p` 访问 `myFixedField` 中的一个元素。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-134">The variable `p` accesses one element in `myFixedField`.</span></span> <span data-ttu-id="cfd4a-135">无需声明单独的 `int*` 变量。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-135">You don't need to declare a separate `int*` variable.</span></span> <span data-ttu-id="cfd4a-136">请注意，你仍然需要 `unsafe` 上下文。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-136">Note that you still need an `unsafe` context.</span></span> <span data-ttu-id="cfd4a-137">在早期版本的 C# 中，需要声明第二个固定的指针：</span><span class="sxs-lookup"><span data-stu-id="cfd4a-137">In earlier versions of C#, you need to declare a second fixed pointer:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

<span data-ttu-id="cfd4a-138">有关详细信息，请参阅有关 [`fixed` 语句](../language-reference/keywords/fixed-statement.md)的文章。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-138">Fore more information, see the article on the [`fixed` statement](../language-reference/keywords/fixed-statement.md).</span></span>

### <a name="ref-local-variables-may-be-reassigned"></a><span data-ttu-id="cfd4a-139">可能会重新分配 `ref` 局部变量</span><span class="sxs-lookup"><span data-stu-id="cfd4a-139">`ref` local variables may be reassigned</span></span>

<span data-ttu-id="cfd4a-140">现在，在对 `ref` 局部变量进行初始化后，可能会对其重新分配，以引用不同的实例。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-140">Now, `ref` locals may be reassigned to refer to different instances after being initialized.</span></span> <span data-ttu-id="cfd4a-141">以下代码现在编译：</span><span class="sxs-lookup"><span data-stu-id="cfd4a-141">The following code now compiles:</span></span>

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

<span data-ttu-id="cfd4a-142">有关详细信息，请参阅有关 [`ref` 返回和 `ref` 局部变量](../programming-guide/classes-and-structs/ref-returns.md)以及 [`foreach`](../language-reference/keywords/foreach-in.md) 的文章。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-142">For more information, see the article on [`ref` returns and `ref` locals](../programming-guide/classes-and-structs/ref-returns.md), and the article on [`foreach`](../language-reference/keywords/foreach-in.md).</span></span>

### <a name="stackalloc-arrays-support-initializers"></a><span data-ttu-id="cfd4a-143">`stackalloc` 数组支持初始值设定项</span><span class="sxs-lookup"><span data-stu-id="cfd4a-143">`stackalloc` arrays support initializers</span></span>

<span data-ttu-id="cfd4a-144">当你对数组中的元素的值进行初始值设定时，你已能够指定该值：</span><span class="sxs-lookup"><span data-stu-id="cfd4a-144">You've been able to specify the values for elements in an array when you initialize it:</span></span>

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

<span data-ttu-id="cfd4a-145">现在，可向使用 `stackalloc` 进行声明的数组应用同一语法：</span><span class="sxs-lookup"><span data-stu-id="cfd4a-145">Now, that same syntax can be applied to arrays that are declared with `stackalloc`:</span></span>

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

<span data-ttu-id="cfd4a-146">有关详细信息，请参阅语言参考中的 [`stackalloc` 语句](../language-reference/keywords/stackalloc.md)一文。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-146">For more information, see the [`stackalloc` statement](../language-reference/keywords/stackalloc.md) article in the language reference.</span></span>

### <a name="more-types-support-the-fixed-statement"></a><span data-ttu-id="cfd4a-147">更多类型支持 `fixed` 语句</span><span class="sxs-lookup"><span data-stu-id="cfd4a-147">More types support the `fixed` statement</span></span>

<span data-ttu-id="cfd4a-148">`fixed` 语句支持有限的一组类型。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-148">The `fixed` statement supported a limited set of types.</span></span> <span data-ttu-id="cfd4a-149">从 C# 7.3 开始，任何包含返回 `ref T` 或 `ref readonly T` 的 `GetPinnableReference()` 方法的类型均有可能为 `fixed`。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-149">Starting with C# 7.3, any type that contains a `GetPinnableReference()` method that returns a `ref T` or `ref readonly T` may be `fixed`.</span></span> <span data-ttu-id="cfd4a-150">添加此功能意味着 `fixed` 可与 <xref:System.Span%601?displayProperty=nameWithType> 和相关类型配合使用。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-150">Adding this feature means that `fixed` can be used with <xref:System.Span%601?displayProperty=nameWithType> and related types.</span></span>

<span data-ttu-id="cfd4a-151">有关详细信息，请参阅语言参考中的 [`fixed` 语句](../language-reference/keywords/fixed-statement.md)一文。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-151">For more information, see the [`fixed` statement](../language-reference/keywords/fixed-statement.md) article in the language reference.</span></span>

### <a name="enhanced-generic-constraints"></a><span data-ttu-id="cfd4a-152">增强的泛型约束</span><span class="sxs-lookup"><span data-stu-id="cfd4a-152">Enhanced generic constraints</span></span>

<span data-ttu-id="cfd4a-153">现在，可以将类型 <xref:System.Enum?displayProperty=nameWithType> 或 <xref:System.Delegate?displayProperty=nameWithType> 指定为类型参数的基类约束。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-153">You can now specify the type <xref:System.Enum?displayProperty=nameWithType> or <xref:System.Delegate?displayProperty=nameWithType> as base class constraints for a type parameter.</span></span>

<span data-ttu-id="cfd4a-154">现在也可以使用新的 `unmanaged` 约束来指定类型参数必须为“非托管类型”。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-154">You can also use the new `unmanaged` constraint, to specify that a type parameter must be an **unmanaged type**.</span></span> <span data-ttu-id="cfd4a-155">“非托管类型”不是引用类型，且在任何嵌套级别都不包含任何引用类型。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-155">An **unmanaged type** is a type that isn't a reference type and doesn't contain any reference type at any level of nesting.</span></span>

<span data-ttu-id="cfd4a-156">有关详细信息，请参阅有关 [`where` 泛型约束](../language-reference/keywords/where-generic-type-constraint.md)和[类型参数的约束](../programming-guide/generics/constraints-on-type-parameters.md)的文章。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-156">For more information, see the articles on [`where` generic constraints](../language-reference/keywords/where-generic-type-constraint.md) and [constraints on type parameters](../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="make-existing-features-better"></a><span data-ttu-id="cfd4a-157">提升了现有功能</span><span class="sxs-lookup"><span data-stu-id="cfd4a-157">Make existing features better</span></span>

<span data-ttu-id="cfd4a-158">第二个主题提供了对语言中的功能的改进。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-158">The second theme provides improvements to features in the language.</span></span> <span data-ttu-id="cfd4a-159">这些功能提升了在编写 C# 时的效率。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-159">These features improve productivity when writing C#.</span></span>

### <a name="tuples-support--and-"></a><span data-ttu-id="cfd4a-160">元组支持 `==` 和 `!=`</span><span class="sxs-lookup"><span data-stu-id="cfd4a-160">Tuples support `==` and `!=`</span></span>

<span data-ttu-id="cfd4a-161">C# 元组类型现在支持 `==` 和 `!=`。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-161">The C# tuple types now support `==` and `!=`.</span></span> <span data-ttu-id="cfd4a-162">有关详细信息，请参阅有关[元组](../tuples.md)文章中的转换[等式](../tuples.md#equality-and-tuples)部分。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-162">Fore more information, see the section covering [equality](../tuples.md#equality-and-tuples) in the article on [tuples](../tuples.md).</span></span>

### <a name="attach-attributes-to-the-backing-fields-for-auto-implemented-properties"></a><span data-ttu-id="cfd4a-163">将属性添加到自动实现的属性的支持字段</span><span class="sxs-lookup"><span data-stu-id="cfd4a-163">Attach attributes to the backing fields for auto-implemented properties</span></span>

<span data-ttu-id="cfd4a-164">现在支持此语法：</span><span class="sxs-lookup"><span data-stu-id="cfd4a-164">This syntax is now supported:</span></span>

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

<span data-ttu-id="cfd4a-165">属性 `SomeThingAboutFieldAttribute` 应用于编译器生成的 `SomeProperty` 的支持字段。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-165">The attribute `SomeThingAboutFieldAttribute` is applied to the compiler generated backing field for `SomeProperty`.</span></span> <span data-ttu-id="cfd4a-166">有关详细信息，请参阅 C# 编程指南中的[属性](../programming-guide/concepts/attributes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-166">For more information, see [attributes](../programming-guide/concepts/attributes/index.md) in the C# programming guide.</span></span>

### <a name="in-method-overload-resolution-tiebreaker"></a><span data-ttu-id="cfd4a-167">`in` 方法重载解析决胜属性</span><span class="sxs-lookup"><span data-stu-id="cfd4a-167">`in` method overload resolution tiebreaker</span></span>

<span data-ttu-id="cfd4a-168">在添加 `in` 参数修饰符时，这两个方法将导致多义性：</span><span class="sxs-lookup"><span data-stu-id="cfd4a-168">When the `in` argument modifier was added, these two methods would cause an ambiguity:</span></span>

```csharp
static void M(S arg);
static void M(in S arg);
```

<span data-ttu-id="cfd4a-169">现在，通过值（前面示例中的第一个）的重载比通过只读引用版本的重载更好。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-169">Now, the by value (first in the preceding example) overload is better than the by readonly reference version.</span></span> <span data-ttu-id="cfd4a-170">若要使用只读引用参数调用版本，必须在调用方法前添加 `in` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-170">To call the version with the readonly reference argument, you must include the `in` modifier when calling the method.</span></span>

> [!NOTE]
> <span data-ttu-id="cfd4a-171">这将作为 bug 修复来实现。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-171">This was implemented as a bug fix.</span></span> <span data-ttu-id="cfd4a-172">即使在设置为“7.2”的语言版本中，这也不再具有多义性。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-172">This no longer is ambiguous even with the language version set to "7.2".</span></span>

<span data-ttu-id="cfd4a-173">有关详细信息，请参阅有关 [`in` 参数修饰符](../language-reference/keywords/in-parameter-modifier.md)的文章。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-173">For more information, see the article on the [`in` parameter modifier](../language-reference/keywords/in-parameter-modifier.md).</span></span>

### <a name="extend-expression-variables-in-initializers"></a><span data-ttu-id="cfd4a-174">扩展初始值设定项中的表达式变量</span><span class="sxs-lookup"><span data-stu-id="cfd4a-174">Extend expression variables in initializers</span></span>

<span data-ttu-id="cfd4a-175">已对在 C# 7.0 中添加的允许 `out` 变量声明的语法进行了扩展，以包含字段初始值设定项、属性初始值设定项、构造函数初始值设定项和查询子句。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-175">The syntax added in C# 7.0 to allow `out` variable declarations has been extended to include field initializers, property initializers, constructor initializers, and query clauses.</span></span> <span data-ttu-id="cfd4a-176">它允许使用如以下示例中所示的代码：</span><span class="sxs-lookup"><span data-stu-id="cfd4a-176">It enables code such as the following example:</span></span>

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : B(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

### <a name="improved-overload-candidates"></a><span data-ttu-id="cfd4a-177">改进了重载候选项</span><span class="sxs-lookup"><span data-stu-id="cfd4a-177">Improved overload candidates</span></span>

<span data-ttu-id="cfd4a-178">在每个版本中，对重载解析规则进行了更新，以解决多义方法调用具有“明显”选择的情况。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-178">In every release, the overload resolution rules get updated to address situations where ambiguous method invocations have an "obvious" choice.</span></span> <span data-ttu-id="cfd4a-179">此版本添加了三个新规则，以帮助编译器选取明显的选择：</span><span class="sxs-lookup"><span data-stu-id="cfd4a-179">This release adds three new rules to help the compiler pick the obvious choice:</span></span>

1. <span data-ttu-id="cfd4a-180">当方法组同时包含实例和静态成员时，如果方法在不含实例接收器或上下文的情况下被调用，则编译器将丢弃实例成员。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-180">When a method group contains both instance and static members, the compiler discards the instance members if the method was invoked without an instance receiver or context.</span></span> <span data-ttu-id="cfd4a-181">如果方法在含有实例接收器的情况下被调用，则编译器将丢弃静态成员。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-181">The compiler discards the static members if the method was invoked with an instance receiver.</span></span> <span data-ttu-id="cfd4a-182">在没有接收器时，编译器将仅添加静态上下文中的静态成员，否则，将同时添加静态成员和实例成员。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-182">When there is no receiver, the compiler includes only static members in a static context, otherwise both static and instance members.</span></span> <span data-ttu-id="cfd4a-183">当接收器是不明确的实例或类型时，编译器将同时添加两者。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-183">When the receiver is ambiguously an instance or type, the compiler includes both.</span></span> <span data-ttu-id="cfd4a-184">静态上下文（其中隐式 `this` 实例接收器无法使用）包含未定义 `this` 的成员的正文（例如，静态成员），以及不能使用 `this` 的位置（例如，字段初始值设定项和构造函数初始值设定项）。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-184">A static context, where an implicit `this` instance receiver cannot be used, includes the body of members where no `this` is defined, such as static members, as well as places where `this` cannot be used, such as field initializers and constructor-initializers.</span></span>
1. <span data-ttu-id="cfd4a-185">当一个方法组包含类型参数不满足其约束的某些泛型方法时，这些成员将从候选集中移除。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-185">When a method group contains some generic methods whose type arguments do not satisfy their constraints, these members are removed from the candidate set.</span></span>
1. <span data-ttu-id="cfd4a-186">对于方法组转换，返回类型与委托的返回类型不匹配的候选方法将从集中移除。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-186">For a method group conversion, candidate methods whose return type doesn't match up with the delegate's return type are removed from the set.</span></span>

<span data-ttu-id="cfd4a-187">你将注意到此更改，因为当你确定哪个方法更好时，你将发现多义方法重载具有更少的编译器错误。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-187">You'll only notice this change because you'll find fewer compiler errors for ambiguous method overloads when you are sure which method is better.</span></span>

## <a name="new-compiler-options"></a><span data-ttu-id="cfd4a-188">新的编译器选项</span><span class="sxs-lookup"><span data-stu-id="cfd4a-188">New compiler options</span></span>

<span data-ttu-id="cfd4a-189">新的编译器选项支持 C# 程序的新版本和 DevOps 方案。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-189">New compiler options support new build and DevOps scenarios for C# programs.</span></span>

### <a name="public-or-open-source-signing"></a><span data-ttu-id="cfd4a-190">公共或开放源代码签名</span><span class="sxs-lookup"><span data-stu-id="cfd4a-190">Public or Open Source signing</span></span>

<span data-ttu-id="cfd4a-191">`-publicsign` 编译器选项指示编译器使用公钥对程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-191">The `-publicsign` compiler option instructs the compiler to sign the assembly using a public key.</span></span> <span data-ttu-id="cfd4a-192">程序集被标记为已签名，但签名取自公钥。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-192">The assembly is marked as signed, but the signature is taken from the public key.</span></span> <span data-ttu-id="cfd4a-193">此选项使你能够使用公钥在开放源代码项目中构建签名的程序集。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-193">This option enables you to build signed assemblies from open-source projects using a public key.</span></span>

<span data-ttu-id="cfd4a-194">有关详细信息，请参阅 [-publicsign 编译器选项](../language-reference/compiler-options/publicsign-compiler-option.md)一文。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-194">For more information, see the [-publicsign compiler option](../language-reference/compiler-options/publicsign-compiler-option.md) article.</span></span>

### <a name="pathmap"></a><span data-ttu-id="cfd4a-195">pathmap</span><span class="sxs-lookup"><span data-stu-id="cfd4a-195">pathmap</span></span>

<span data-ttu-id="cfd4a-196">`-pathmap` 编译器选项指示编译器将生成环境中的源路径替换为映射的源路径。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-196">The `-pathmap` compiler option instructs the compiler to replace source paths from the build environment with mapped source paths.</span></span> <span data-ttu-id="cfd4a-197">`-pathmap` 选项控制由编译器编写入 PDB 文件或为 <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> 编写的源路径。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-197">The `-pathmap` option controls the source path written by the compiler to PDB files or for the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span></span>

<span data-ttu-id="cfd4a-198">有关详细信息，请参阅 [-pathmap 编译器选项](../language-reference/compiler-options/pathmap-compiler-option.md)一文。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-198">For more information, see the [-pathmap compiler option](../language-reference/compiler-options/pathmap-compiler-option.md) article.</span></span>