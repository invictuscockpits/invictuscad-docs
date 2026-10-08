# Combine and Split Bodies

## Combine

**MODIFY › Combine** joins bodies together, cuts one with others, or keeps only where they overlap.

1. Choose **MODIFY › Combine**.
2. Pick the **Body** that changes.
3. Pick the **Tools**: the other bodies.
4. Choose the **Operation**: **Join**, **Cut** or **Intersect**.
5. For a cut, set a **Clearance** if you want room around the tools. The tools cut as if they
   were that much bigger all round, so a pin modeled at its exact size leaves a hole it fits in.
6. Turn on **Keep tools** to leave the tool bodies in the design. Otherwise they're hidden once
   they're used; show them again from the browser.
7. Click **OK**.

The combine follows its tools: move or change a tool body and the result updates.

## Split

**MODIFY › Split Body** cuts a body into pieces along a plane or a face.

1. Choose **MODIFY › Split Body**.
2. Pick the **Body** to split.
3. Pick the **Tool**: an origin plane, a [reference plane](reference-planes.md), or a face of
   another body. A curved face works too.
4. Leave **Extend** on to grow the tool across its whole surface, so it cuts right through like a
   plane. Turn it off to cut only where the face itself reaches, or set **Extend by** to grow it
   just that far past its edges.
5. Click **OK**.

The largest piece stays in the body you split. Every other piece becomes a body of its own, which
follows the split if the body or the tool changes.
