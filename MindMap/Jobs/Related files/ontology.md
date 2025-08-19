**Ontology** in data science is a **formal representation of knowledge** that defines entities, their properties, and the relationships between them - going beyond simple hierarchical classification.

## Key Difference from Taxonomy:

- **Taxonomy**: Simple parent-child hierarchies (tree structure)
- **Ontology**: Complex relationships, properties, and rules (network/graph structure)

## Components of Ontology:

1. **Entities/Concepts**: Things that exist (Customer, Product, Order)
2. **Properties/Attributes**: Characteristics (hasPrice, hasColor, hasRating)
3. **Relationships**: How entities connect (customerBuys, productBelongsTo, productSimilarTo)
4. **Rules**: Logical constraints (if X then Y)

## Example - E-commerce Ontology:

```
Entities:
- Customer, Product, Brand, Category, Review

Properties:
- Customer: hasAge, hasLocation, hasPurchaseHistory
- Product: hasPrice, hasRating, hasDescription
- Review: hasRating, hasText, hasDate

Relationships:
- Customer "purchases" Product
- Product "belongsTo" Category  
- Product "manufacturedBy" Brand
- Customer "writes" Review "about" Product
- Product "similarTo" Product

Rules:
- IF Customer purchases Product THEN Customer "has interest in" Category
- IF Product hasRating > 4.5 THEN Product "is highly rated"
```