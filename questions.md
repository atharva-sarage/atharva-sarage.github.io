---
layout: questions
title: Questions
permalink: /questions/
---

Q) What happens when child process free's cow memory?

<details>
  <summary>Ans</summary>
  
  ### Answer
When a child process frees a page that was originally marked as Copy-On-Write (COW) due to fork(), the following happens:

If the child has not modified the page:

The page is still shared between the parent and child.

The free() call does not trigger any page deallocation at the kernel level since the reference count is still greater than zero.

The child's virtual memory mapping is updated to mark the page as free.

If the child had modified the page (triggered COW):

A private copy of the page was already created for the child.

When free() is called, the child’s reference to this private page is dropped.

If no other references exist (i.e., the parent does not have a reference to this private copy), the page is deallocated.

Summary:
If the page is still shared (not written by the child), nothing happens at the physical memory level.

If the child had written to it (breaking COW), its private copy is freed when the child no longer needs it.

This behavior ensures that memory is managed efficiently, avoiding unnecessary duplication while allowing safe modifications.
</details>





---
