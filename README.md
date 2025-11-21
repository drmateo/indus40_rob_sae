# Industry 4.0 Robotic Cell - SAE Project

## Project Overview

**Course Code:** GEII - Industry 4.0 SAE  
**Level:** 3rd Year Engineering (GEII)  
**Language:** English  
**Total Hours:** 52 hours (project-based learning)  
**Prerequisites:** Completion of Industrial Robotics Guided Course (44h)

## Project Description

This SAE (Situation d'Apprentissage et d'Évaluation) is a comprehensive project-based course where students design, simulate, and validate a complete Industry 4.0 robotic cell using the OpenManipulator-X robot. Students will integrate kinematics, trajectory planning, computer vision, and quality control systems to create an automated manufacturing solution.

## Educational Context

This project represents the practical application phase following the guided theoretical course. Students work in teams to solve a realistic industrial problem, demonstrating their mastery of:

- Robot kinematics and control
- Trajectory planning and optimization
- Computer vision integration
- Quality inspection systems
- Industry 4.0 principles
- System integration and testing

## Learning Objectives

By the end of this project, students will be able to:

1. **System Design**
   - Design a complete robotic cell for industrial applications
   - Select appropriate hardware and software components
   - Define system specifications and requirements

2. **Kinematics Implementation**
   - Implement FK/IK for OpenManipulator-X
   - Develop workspace analysis tools
   - Optimize robot placement and configuration

3. **Motion Planning**
   - Design pick-and-place sequences
   - Implement collision-free trajectories
   - Optimize cycle times

4. **Vision Integration**
   - Implement object detection and localization
   - Calibrate camera-robot coordination
   - Handle vision-guided motion

5. **Quality Control**
   - Develop dimensional inspection algorithms
   - Implement defect detection
   - Create quality reporting systems

6. **System Integration**
   - Integrate all subsystems (vision, motion, inspection)
   - Develop supervisory control
   - Implement error handling and recovery

7. **Validation and Testing**
   - Create comprehensive test scenarios
   - Measure system performance
   - Document results and limitations

## Project Scenario

### Industry 4.0 Smart Manufacturing Cell

**Application:** Automated Quality Inspection and Sorting

Students must design and simulate a robotic cell that:

1. **Processes workpieces** from an input conveyor
2. **Inspects quality** using vision and measurements
3. **Sorts products** into OK/NOK (good/defective) bins
4. **Tracks production** metrics and quality statistics
5. **Adapts** to different product variants

### Robot Platform

**OpenManipulator-X Specifications:**
- 5 DOF articulated manipulator
- Workspace: ~350mm radius
- Payload: 500g
- Gripper: 2-finger parallel
- Control: ROS-based (simulated in Python)

### Workpieces

Students work with multiple part types:
- Cylindrical components (varying diameters/heights)
- Rectangular blocks (different dimensions)
- Complex shapes (optional challenge)

### Quality Criteria

Inspection requirements:
- Dimensional tolerance: ±0.5mm
- Surface defect detection
- Color verification (optional)
- Assembly completeness check

## Project Structure (52 hours)

### Session 1: Project Introduction and Setup (4h)
**File:** `SAE_Industry40_Project.ipynb`

**Activities:**
- Project presentation and requirements
- Team formation (2-3 students)
- OpenManipulator-X introduction
- Environment setup and testing
- Initial brainstorming and planning

**Deliverables:**
- Team composition
- Project understanding document
- Initial system architecture sketch

### Session 2: Robot Modeling and Workspace Analysis (8h)
**File:** `SAE_Session2_Motion_Planning.ipynb`

**Part A: Kinematics (4h)**
- Implement OpenManipulator-X FK using DH parameters
- Develop IK solver (analytical or numerical)
- Validate against Robotics Toolbox
- Create workspace visualization

**Part B: Motion Planning (4h)**
- Design pick-and-place trajectories
- Implement joint-space interpolation
- Develop Cartesian path planning
- Test basic motion sequences

**Deliverables:**
- FK/IK implementation and validation
- Workspace analysis report
- Basic trajectory demonstrations

### Session 3: Vision System and Object Localization (8h)
**File:** `SAE_Session3_Quality_Inspection.ipynb`

**Part A: Vision Processing (4h)**
- Simulate camera system
- Implement object detection (centroid, orientation)
- Develop camera-robot calibration
- Test localization accuracy

**Part B: Quality Inspection (4h)**
- Implement dimensional measurement
- Develop defect detection algorithms
- Create OK/NOK classification logic
- Generate inspection reports

**Deliverables:**
- Vision system implementation
- Inspection algorithm validation
- Sample inspection reports

### Session 4: System Integration (8h)
**File:** `SAE_Session4_System_Integration.ipynb`

**Part A: Cell Layout (4h)**
- Design complete cell layout
- Optimize robot placement
- Define I/O zones (input, OK bin, NOK bin)
- Plan material flow

**Part B: Control Integration (4h)**
- Integrate vision and motion systems
- Implement state machine control
- Develop pick-inspect-sort sequence
- Add error handling

**Deliverables:**
- Complete cell design
- Integrated control system
- Basic operation demonstration

### Session 5: Advanced Features and Optimization (8h)
**File:** `SAE_Session5_Advanced_Control.ipynb`

**Part A: Cycle Time Optimization (4h)**
- Analyze current cycle time
- Optimize trajectories for speed
- Implement parallel operations
- Balance speed vs. accuracy

**Part B: Advanced Capabilities (4h)**
- Multi-variant product handling
- Adaptive inspection parameters
- Predictive quality monitoring
- Production scheduling

**Deliverables:**
- Performance optimization report
- Advanced feature demonstrations
- Cycle time analysis

### Session 6: Testing, Validation, and Documentation (8h)
**File:** `SAE_Session6_Testing_Validation.ipynb`

**Part A: Comprehensive Testing (4h)**
- Develop test scenarios
- Execute systematic tests
- Measure KPIs (cycle time, accuracy, reliability)
- Identify and document issues

**Part B: Performance Analysis (4h)**
- Analyze test results
- Create performance dashboard
- Document limitations and improvements
- Prepare demonstration

**Deliverables:**
- Test results and analysis
- Performance metrics report
- Issue log and solutions

### Session 7: Final Integration and Presentation (8h)
**File:** `SAE_Session7_Integration_Documentation.md` (guide)

**Part A: Final Integration (4h)**
- Final system debugging
- Complete documentation
- Prepare demonstration scenarios
- Practice presentation

**Part B: Project Presentation (4h)**
- Live demonstration (15 min/team)
- Q&A with jury
- Peer evaluation
- Final submission

**Deliverables:**
- Complete working system
- Final documentation package
- Presentation slides
- Demo video

## Technical Requirements

### Software Tools

```bash
# Required Python packages
pip install numpy matplotlib scipy
pip install roboticstoolbox-python
pip install spatialmath-python
pip install opencv-python  # For vision simulation
pip install pandas  # For data analysis
pip install jupyter notebook
```

### Simulation Environment

Students will work in a simulated environment that includes:
- OpenManipulator-X robot model
- Simulated camera and vision system
- Virtual conveyor and bins
- Workpiece models
- Measurement simulation

### Code Organization

Expected project structure:
```
team_X_project/
├── kinematics/
│   ├── forward_kinematics.py
│   ├── inverse_kinematics.py
│   └── workspace_analysis.py
├── vision/
│   ├── object_detection.py
│   ├── camera_calibration.py
│   └── quality_inspection.py
├── control/
│   ├── trajectory_planner.py
│   ├── state_machine.py
│   └── error_handler.py
├── integration/
│   ├── main_controller.py
│   ├── cell_layout.py
│   └── performance_monitor.py
├── tests/
│   └── test_scenarios.py
├── docs/
│   ├── technical_report.pdf
│   └── user_manual.md
└── demo/
    └── demonstration.ipynb
```

## Assessment Criteria (100 points)

### Technical Implementation (50 points)

**Kinematics and Motion (15 points)**
- FK/IK correctness and efficiency (7 pts)
- Trajectory planning quality (5 pts)
- Workspace utilization (3 pts)

**Vision and Inspection (15 points)**
- Object detection accuracy (7 pts)
- Quality inspection reliability (5 pts)
- Camera-robot coordination (3 pts)

**System Integration (20 points)**
- Complete system functionality (10 pts)
- Error handling robustness (5 pts)
- Code quality and organization (5 pts)

### Project Management (20 points)

**Planning and Execution (10 points)**
- Project planning effectiveness (5 pts)
- Time management (3 pts)
- Team collaboration (2 pts)

**Documentation (10 points)**
- Technical documentation clarity (5 pts)
- Code documentation (3 pts)
- User manual quality (2 pts)

### Performance and Innovation (20 points)

**System Performance (10 points)**
- Cycle time optimization (4 pts)
- Inspection accuracy (3 pts)
- System reliability (3 pts)

**Innovation and Extras (10 points)**
- Advanced features implementation (5 pts)
- Creative solutions (3 pts)
- Industry 4.0 integration (2 pts)

### Presentation and Demo (10 points)

**Live Demonstration (5 points)**
- System operation smoothness (3 pts)
- Scenario coverage (2 pts)

**Presentation Quality (5 points)**
- Technical communication (3 pts)
- Q&A handling (2 pts)

## Key Performance Indicators (KPIs)

Students must measure and report:

### Primary KPIs
- **Cycle Time:** Complete pick-inspect-sort sequence (target: <30s)
- **Inspection Accuracy:** Correct OK/NOK classification (target: >95%)
- **Positional Accuracy:** Pick/place precision (target: ±1mm)
- **System Uptime:** Successful operation rate (target: >90%)

### Secondary KPIs
- **Throughput:** Parts processed per hour
- **First-Pass Yield:** Parts correctly processed without retry
- **False Positive Rate:** Good parts rejected
- **False Negative Rate:** Defective parts accepted

## Deliverables Timeline

| Session | Due Date | Deliverable |
|---------|----------|-------------|
| 1 | End of Session 1 | Team formation, project plan |
| 2 | End of Session 2 | Kinematics implementation |
| 3 | End of Session 3 | Vision and inspection system |
| 4 | End of Session 4 | Integrated system v1.0 |
| 5 | End of Session 5 | Optimized system |
| 6 | End of Session 6 | Test results and analysis |
| 7 | End of Session 7 | Final system and presentation |

**Final Submission Deadline:** End of Session 7

## Team Organization

### Recommended Roles (rotating)

**Session Lead:** Coordinates session activities  
**Implementation Lead:** Oversees coding  
**Testing Lead:** Validates functionality  
**Documentation Lead:** Maintains documentation

Roles should rotate to ensure all students gain diverse experience.

### Collaboration Guidelines

1. **Use version control** (Git recommended)
2. **Document all decisions** in project log
3. **Review code together** before integration
4. **Test incrementally** don't wait until the end
5. **Communicate regularly** within team
6. **Ask for help** during sessions, not last minute

## Industry 4.0 Concepts Applied

This project incorporates key Industry 4.0 principles:

### Smart Factory Elements
- **Automation:** Robotic manipulation and inspection
- **Digitalization:** Digital twin simulation
- **Data Analytics:** Quality metrics and trends
- **Flexibility:** Multi-variant handling
- **Integration:** Vision-motion-inspection coordination

### Technologies Explored
- Collaborative robotics concepts
- Machine vision systems
- Quality 4.0 (automated inspection)
- Digital manufacturing simulation
- Data-driven decision making

## Common Challenges and Solutions

### Challenge 1: IK Multiple Solutions
**Problem:** Multiple valid joint configurations  
**Solution:** Implement solution selection criteria (closest to current, avoid limits)

### Challenge 2: Vision-Robot Calibration
**Problem:** Coordinate system transformation errors  
**Solution:** Systematic calibration procedure, validation points

### Challenge 3: Trajectory Collisions
**Problem:** Robot hitting workspace boundaries  
**Solution:** Workspace analysis, collision checking, safe trajectories

### Challenge 4: Cycle Time vs. Accuracy
**Problem:** Trade-off between speed and precision  
**Solution:** Optimize critical phases, use faster speeds where possible

### Challenge 5: System Integration
**Problem:** Coordinating multiple subsystems  
**Solution:** State machine design, modular architecture, clear interfaces

## Resources and References

### OpenManipulator-X Documentation
- Technical specifications
- URDF/DH parameters
- Workspace characteristics
- Control interfaces

### Industry 4.0 Resources
- Smart manufacturing principles
- Quality 4.0 guidelines
- Robotic cell design standards
- Safety considerations

### Programming Resources
- Python best practices
- Robotics Toolbox examples
- OpenCV tutorials
- NumPy/SciPy documentation

## Connection to Professional Practice

This project simulates real-world challenges in:

- **Manufacturing Engineering:** Cell design and optimization
- **Automation Engineering:** System integration and control
- **Quality Engineering:** Inspection system development
- **Robotics Engineering:** Motion planning and kinematics
- **Software Engineering:** Modular design and testing

Skills developed are directly applicable to:
- Industrial automation projects
- Robotic system integration
- Quality assurance systems
- Production line optimization
- Smart factory implementations

## Support and Resources

### During Sessions
- Instructor available for guidance
- Technical documentation provided
- Example code snippets
- Debugging assistance

### Between Sessions
- Online forum for questions
- Shared resource repository
- Team collaboration tools
- Office hours (by appointment)

## Final Presentation Guidelines

### Presentation Structure (15 minutes)

1. **Introduction (2 min)**
   - Team and project overview
   - Problem statement
   - Proposed solution

2. **Technical Approach (5 min)**
   - System architecture
   - Key algorithms and implementations
   - Challenges and solutions

3. **Live Demonstration (5 min)**
   - Complete pick-inspect-sort cycle
   - Different scenarios (OK/NOK parts)
   - System monitoring dashboard

4. **Results and Analysis (2 min)**
   - KPI achievements
   - Performance analysis
   - Lessons learned

5. **Q&A (5-10 min)**
   - Jury questions
   - Technical discussion

### Demonstration Scenarios

Must demonstrate:
1. Normal operation (OK part)
2. Defect detection (NOK part)
3. Multi-variant handling
4. Error recovery
5. Performance monitoring

## Academic Integrity

- **Original work required:** No copying from other teams
- **Citations needed:** Reference any external code/resources
- **Collaboration allowed:** Within team, learning together
- **Consultation permitted:** Ask instructor, use documentation
- **Sharing prohibited:** Don't share code with other teams

Violations will result in penalties according to university policy.

## Success Criteria

A successful project demonstrates:

✓ Complete functional system  
✓ All core requirements met  
✓ Good code quality and documentation  
✓ Measured performance meeting targets  
✓ Effective team collaboration  
✓ Professional presentation  
✓ Understanding of concepts applied  
✓ Critical analysis of results  

## Expected Outcomes

Upon completion, students will have:

- Designed and implemented a complete robotic system
- Integrated multiple technologies (vision, motion, control)
- Applied theoretical knowledge to practical problems
- Developed professional engineering skills
- Created a portfolio-worthy project
- Gained Industry 4.0 experience
- Enhanced teamwork and communication abilities

## Next Steps After SAE

This project prepares students for:

- **Internships** in robotics and automation companies
- **Advanced courses** in robot control and AI
- **Capstone projects** with industrial partners
- **Research projects** in robotics laboratories
- **Career opportunities** in Industry 4.0 sectors

---

**Last Updated:** November 2025  
**Version:** 1.0  

**Note:** This SAE builds directly on the Industrial Robotics Guided Course (44h). Ensure prerequisite knowledge before starting this project.

*Good luck with your Industry 4.0 robotic cell project!*
