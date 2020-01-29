# EOType:

Magma code for computing Ekedahl-Oort types of curves (function fields) over finite fields


Importing:
----------

To use the code in Magma simply attach the EOType file

```
Attach("EOType.mag");
```

Examples:
---------

The two files 

* ExampleHyperellipticEO.mag 
* ExamplePrymEO.mag 

contain examples to compute lists of EOtypes of Jacobians of curves and Prym varieties respectively 

---

# Documentation:

The documentation is a bit light (apologies). Included in the folder is what is below and some slides from a (funny at the time) talk I gave on this codebase at the Canadian Mathematics Society Winter Meeting in December 2018. 


## Main functions:

The main function of this code base is EOType(Kn:FldFun) which returns the sequence corresponding to the
Ekedahl-Oort type of the p-torsion of the Jacobian of the curve corresponding to the input function field. 

```
EOType(Kn::FldFun) -> SeqEnum
  {Return the lenght 2g sequence of the Ekedahl-Oort type of Kn}
```

## Basic functions on EO Types:

```
ExtendEO(EO::SeqEnum) -> SeqEnum
  {Given a length g EO type return the length 2g type}
```

```
IsValidEO(EO::SeqEnum) -> BoolElt
  {Checks if the length 2g sequence is a valid symmetric BT1 EO-type}
```

```
DecomposeEO(EO::SeqEnum) -> SetMulti[SeqEnum]
  {Return the EO type of each irreducible submodule}
```

```
ComposeEO(EOset::SetMulti) -> SeqEnum
  {Turns a multiset of EOs into a single EO} 
```

##  EO types of (mod p) Dieudonne modules (which we call (F,V)-modules) 

```
H1dR(K::FldFun) -> ModRng
  {Return the (F,V)-module of dimension 2g}
```

```
EOType(D::ModRng) -> SeqEnum
  {Computes the EO type of the (F,V)-module}
```

```
FVModule(EO::SeqEnum , p::RngIntElt) ->  ModRng
  {Return the canonical (F,V)-module (over GF(p)) for a given type}
```	

## Conversion functions between presentations:

There are many equivalent ways to descibe the isomorphism type of a Dieudonne module. 
Below are a series of functions that convert between several of these different representations. 

```
EOToPermutation(EO::SeqEnum)-> GrpPermElt
  {EO to Permutation}
```

```
PermutationToEO(c::GrpPermElt) -> SeqEnum
  {Permutation to EO}
```

```
PermutationToEO(c::SeqEnum) -> SeqEnum
  {Permutation to EO}
```

```
EOToFVRelations(EO::SeqEnum : P:=FreeGroup(2)) -> SetMulti[GrpPerm]
  {Return the (F,V)-module relations of the components}
  The group P is an optional parameter so the user can provide an <F,V> group globally. 
```

```
FVRelationToEO(FVelt::GrpFPElt) -> SeqEnum
  {Return the (F,V)-module relations to an EO type}
```

```
FVRelationsToEO(FVelts::SetMulti) -> SeqEnum
  {From a collection of (F,V)-module relations to an EO type}   
```


	
	
	
	
	
	
	
	


