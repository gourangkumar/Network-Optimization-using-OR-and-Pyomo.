# Network-Optimization-using-OR-and-Pyomo.
Solving Operation Research illustration while finding the shortest distance and time consumed.
Answers:
1)
Following are the decision variable, parameters and indices used:
Decision variable
xij = Binary variable indicating whether school ‘I’ is closed (1) or not (0).
yijk = Binary variable indicating whether grade ‘k’ from school ‘i’ is relocated to school ‘j’
Parameters:
Eij: Enrolment in grade ‘i’ at school ‘j’.
D: Maximum distance allowed for relocation (1 km).
T: Minimum total enrolment threshold for a school to remain open (50).
Dij: Distance between school ‘I’ and school ‘j’.
Indices:
i, j, k: Schools, schools, and grades, respectively.
Constraints
1. Each grade should be relocated to only one school:
∑_(j=1)^n▒y_ijk = 1
2. Total enrolment of the relocated grades should meet the minimum threshold if the school is closed:
∑_(j=1)^n▒∑_(k=1)^12▒E_ij ⋅ y_ijk≥ T ⋅ x_ij∀ i

3. A school can be closed only if all grades it serves can be relocated within the maximum distance:
∑_({k=1}_{ijk}^{12}y)▒y≤D ⋅x_({ij}  )∀i

4. Binary constraints on decision variables:
x_{ij} ,y_{ijk} ∈\{0,1\}
Objective Function:
Minimize the total travel distance post the closure of schools:
∑_(i,j)▒(D_(i,j) ) ⋅y_ijk
