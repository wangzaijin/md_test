# md_test
markdown test


# 1
## 2
### 3
##### 🚀 attachment format
```
  "objects": {
  "toy_69_link": {            
            .
            .
            .
            "articulated": false,
            "link": [
                "toy_69_link"
            ],
            "attachments": [
                {
                    "attach_name": <attachment-name-id-str>,
                    "attach_link": <attach-locaction-link-str>,
                    "base_link": <attach-object-base-link-str>,
                    "attach_trans": [x, y, z],
                    "attach_orient": [w, x, y, z],  
                    "cartesian_constraint_coeff": [x_coef, y_coef, z_coef, r_coef, p_coef, y_coef]
                }
            ]
        },
        
    }   
```
    
**Note that:**


- attachments specify how the robot will 'grasp' the object
   + attach_trans and attach_orient is the transformation from the attached link to the robot end effector (i.e., represent the end effector in attached link frame).
+ cartesian_constraint_coeff is a 6D vector that defines the DoF of baselink of attached object
   + [x_coef, y_coef, z_coef, r_coef, p_coef, y_coef]
   + Each coefficient constrains freedom of a DoF, where 0 refers to free and 1 refers to fixed.
   + For example, [1, 1, 1, 1, 1, 1] indicates a fixed baselink object.
   + [0, 0, 1, 1, 1, 1] indicates a baselink whose x axis and y axis could be manipulated.
   + [0, 0, 0, 0, 0, 0] indicates a floating (6 DoF) baselink



+ ik_cost_coeff define the cost coefficient of actuating a robot joint

   +The number of coefficients must be greater than, or equal to, the number of joints of the robot, and less than, or equal to, the number of joints in VKC. The number of joints in VKC includes robot joints and manipulated object joints.

1111
