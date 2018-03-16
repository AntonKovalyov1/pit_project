# pit_project
PIT mutation testing system new operators

New operators added:
  1. AOD: Replaces an arithmetic expression by each one of the operand, e.g., a + b -> a and a + b -> b.
  2. ROR: Replaces the relational operators with each of the other ones, e.g., < -> ==, < -> !=, < -> ≥, < -> >, and < -> ≤.
  3. AOR: Replaces an arithmetic expression by each of the other ones, e.g., a + b -> a - b, a + b -> a * b, a + b -> a / b, a + b -> a % b.
  
To run new operators on a project, add the following to the POM of your project in build/plugins:

            <plugin>
                <groupId>org.pitest</groupId>
                <artifactId>pitest-maven</artifactId>
                <version>1.4.0-SNAPSHOT</version>
                <configuration>
                    <mutators>
                        <mutator>CUSTOM</mutator>
                    </mutators>
                </configuration>
            </plugin>
            
CUSTOM includes all new operators, you can also add other mutators or declare the new mutators one by one, e.g., <mutator>ROR</mutator>
For more information and to change other configurations visit http://pitest.org/quickstart/maven/