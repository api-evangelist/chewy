# Chewy GraphQL Schema

## Overview

This document describes a conceptual GraphQL schema for the Chewy pet supplies e-commerce platform. Chewy is one of the largest online pet retailers in the United States, offering pet food, supplies, pharmacy, telehealth, and subscription Autoship services. While Chewy does not currently publish a public consumer-facing GraphQL API, this schema models the core domain objects that underpin their platform based on publicly available product, service, and vendor integration documentation.

## Schema Source

This schema is conceptual and derived from:

- Chewy public website and product catalog structure (https://www.chewy.com)
- Chewy Pharmacy and prescription fulfillment services (https://www.chewy.com/app/content/chewy-pharmacy)
- Connect With a Vet telehealth service descriptions (https://www.chewy.com/app/content/connect-with-a-vet)
- Chewy Autoship subscription program documentation
- Dsco vendor integration platform (https://www.dsco.io) used for Chewy supplier EDI
- Chewy investor relations and newsroom disclosures (https://investor.chewy.com)

## Domain Coverage

The schema covers the following primary domains:

### Pets and Pet Profiles
Types for modeling pet owners and their animals, including species, breed, age, weight, and health history. Supports multi-pet households as a first-class concept.

### Health and Veterinary
Medical records, prescriptions, medications, and vet partnerships. Reflects Chewy Pharmacy prescription fulfillment and Connect With a Vet telehealth integration.

### Product Catalog
Full product hierarchy including food types (dry, wet, raw, prescription diet, specialty diet), toys, treats, grooming supplies, medical supplies, and general pet supplies. Products are organized by category, brand, and species suitability.

### Autoship Subscriptions
Subscription order management covering frequency, discount tiers, recipient pets, and upcoming delivery scheduling. Autoship is a core revenue driver for Chewy.

### Orders and Fulfillment
Order lifecycle from placement through delivery and returns, including tracking, shipping details, and delivery date estimation.

### Customer and Account
Customer profiles, addresses, payment methods, AutoPay enrollment, and rewards program (Paw Points) balance and transaction history.

### Vendor Integration
API key management, tokens, and webhook configuration reflecting Chewy's Dsco-based supplier integration model.

## Types Summary

The schema defines 65 named GraphQL types across these domains:

| Domain | Types |
|---|---|
| Pets and Profiles | Pet, PetProfile, PetDetails, Species, Breed, Age, Weight |
| Health and Veterinary | Health, MedicalRecord, Medication, Prescription, VetRecord, Veterinarian, VetPartner, VetClinic |
| Products | Product, ProductDetails, ProductCategory, Brand, ProductImage, Ingredient, Nutritional, FoodType, PetFood, DryFood, WetFood, RawFood, PrescriptionDiet, SpecialtyDiet, Toy, Treat, Supplies, MedicalSupply, GroomingSupply, ProductSKU |
| Pricing | Price, SalePrice, AutoshipDiscount |
| Autoship | Autoship, AutoshipOrder, AutoshipDetails, AutoshipFrequency, RecipientPet |
| Orders | Order, OrderItem, OrderStatus, OrderTracking, Shipping, DeliveryDate, Returns, Item |
| Customer | Customer, PetOwner, CustomerProfile, Address, PaymentMethod, AutoPay, Rewards, RewardPoints, PawPoints |
| Auth and Integration | APIKey, Token, Webhook |

## GraphQL File

See `chewy-schema.graphql` for the full type definitions.
