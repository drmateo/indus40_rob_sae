# Quick Start Guide - Industry 4.0 SAE Project

## Getting Started with Your Team Project

### Prerequisites Check ✓

Before starting, ensure you have completed:
- [x] Industrial Robotics Guided Course (44h)
- [x] TP 00-05 (all practical sessions)
- [x] Understanding of FK/IK, Jacobian, Trajectories
- [x] Proficiency with Python, NumPy, Matplotlib
- [x] Experience with Robotics Toolbox

### Environment Setup

```bash
# Navigate to SAE project directory
cd indus40_rob_sae

# Use the same virtual environment from guided course
source ../indus40_rob/venv/bin/activate  # Linux/Mac
# or
..\indus40_rob\venv\Scripts\activate  # Windows

# Install additional packages for SAE
pip install opencv-python pandas scikit-learn
```

### Verify Installation

```python
# Run this in Jupyter notebook
import numpy as np
import matplotlib.pyplot as plt
import roboticstoolbox as rtb
from spatialmath import SE3
import cv2  # OpenCV for vision
import pandas as pd  # For data analysis

print("✓ All packages imported successfully!")
```

## Project Overview - Quick Facts

**What:** Design and simulate an Industry 4.0 robotic quality inspection cell  
**Robot:** OpenManipulator-X (5-DOF)  
**Task:** Automated pick-inspect-sort system  
**Duration:** 52 hours (7 sessions)  
**Team Size:** 2-3 students  
**Deliverables:** Working system + documentation + presentation

## 7-Session Roadmap

### Session 1 (4h) - Project Launch
**File:** `SAE_Industry40_Project.ipynb`

**Goals:**
- Form teams
- Understand requirements
- Setup environment
- Create project plan

**Quick Tasks:**
1. Read project description thoroughly
2. Assign team roles
3. Sketch initial system design
4. Test OpenManipulator-X model

### Session 2 (8h) - Motion Foundation
**File:** `SAE_Session2_Motion_Planning.ipynb`

**Goals:**
- Implement robot kinematics
- Develop motion planner
- Create workspace analysis

**Quick Tasks:**
1. Define DH parameters for OpenManipulator-X
2. Code FK function
3. Code IK solver
4. Test pick-and-place trajectory

### Session 3 (8h) - Vision & Inspection
**File:** `SAE_Session3_Quality_Inspection.ipynb`

**Goals:**
- Simulate camera system
- Detect and localize objects
- Implement quality checks

**Quick Tasks:**
1. Create simulated camera view
2. Detect object positions
3. Implement measurement algorithms
4. Test OK/NOK classification

### Session 4 (8h) - Integration
**File:** `SAE_Session4_System_Integration.ipynb`

**Goals:**
- Design complete cell layout
- Integrate all subsystems
- Implement control logic

**Quick Tasks:**
1. Define cell layout (conveyor, bins, robot)
2. Integrate vision and motion
3. Create state machine
4. Test complete cycle

### Session 5 (8h) - Optimization
**File:** `SAE_Session5_Advanced_Control.ipynb`

**Goals:**
- Optimize cycle time
- Add advanced features
- Improve robustness

**Quick Tasks:**
1. Measure baseline performance
2. Optimize trajectories
3. Add multi-variant handling
4. Implement error recovery

### Session 6 (8h) - Testing & Validation
**File:** `SAE_Session6_Testing_Validation.ipynb`

**Goals:**
- Comprehensive testing
- Performance measurement
- Documentation

**Quick Tasks:**
1. Create test scenarios
2. Run systematic tests
3. Measure all KPIs
4. Document results

### Session 7 (8h) - Final Demo
**Guide:** `SAE_Session7_Integration_Documentation.md`

**Goals:**
- Final integration
- Presentation preparation
- Live demonstration

**Quick Tasks:**
1. Final debugging
2. Prepare demo scenarios
3. Create presentation
4. Practice demo

## Team Organization

### Day 1: Choose Roles

Assign rotating roles:
- **Project Manager:** Coordinates activities, tracks progress
- **Lead Developer:** Oversees code integration
- **QA Lead:** Testing and validation
- **Documentation Lead:** Maintains all documents

**Rotate roles every 2 sessions** to ensure everyone gains diverse experience.

### Day 1: Create Team Repository

```bash
# Create project folder
mkdir team_X_project
cd team_X_project

# Initialize git (recommended)
git init
git add .
git commit -m "Initial project setup"

# Create folder structure
mkdir -p kinematics vision control integration tests docs demo
```

## Critical Success Factors

### ✅ Do This

1. **Start Simple**
   - Get basic functionality working first
   - Add complexity incrementally
   - Test each component separately

2. **Plan Ahead**
   - Sketch architecture before coding
   - Define interfaces between modules
   - Allocate time for integration

3. **Test Continuously**
   - Test after every major change
   - Keep simple test cases
   - Don't wait until the end

4. **Document as You Go**
   - Comment your code
   - Keep a project log
   - Document decisions

5. **Communicate**
   - Daily check-ins with team
   - Share progress and issues
   - Ask instructor when stuck

### ❌ Avoid This

1. **Don't overthink initially** - Start with minimum viable product
2. **Don't work in silos** - Integrate early and often
3. **Don't skip validation** - Always verify against requirements
4. **Don't leave docs for last** - Document continuously
5. **Don't panic** - Instructor is there to help

## OpenManipulator-X Quick Reference

### Robot Specifications

```python
# DH Parameters (example - verify in session 2)
# Joint | theta | d    | a    | alpha
# 1     | q1    | 0.077| 0    | π/2
# 2     | q2    | 0    | 0.13 | 0
# 3     | q3    | 0    | 0.124| 0
# 4     | q4    | 0    | 0.126| 0
# 5     | q5    | 0.077| 0    | 0

# Workspace
radius_max = 0.35  # meters
height_max = 0.40  # meters

# Joint Limits (example)
q_min = np.array([-π, -π/2, -π/2, -π/2, -π])
q_max = np.array([π, π/2, π/2, π/2, π])

# Payload
max_payload = 0.5  # kg
```

### Quick FK Test

```python
import numpy as np
import roboticstoolbox as rtb

# You'll implement your own, but here's how to check
# with Robotics Toolbox

# For OpenManipulator, you might create:
# (This is simplified - you'll define properly in Session 2)

def quick_fk_test(q):
    """Quick FK test function"""
    # Your FK implementation here
    T = your_fk_function(q)
    print(f"End-effector position: {T[:3, 3]}")
    return T
```

## Common Scenarios to Implement

### Scenario 1: Basic Pick-Place
```
1. Wait for object at input
2. Detect object position
3. Move to pre-grasp pose
4. Grasp object
5. Lift object
6. Move to inspection zone
7. Inspect quality
8. Move to appropriate bin (OK/NOK)
9. Release object
10. Return to home position
```

### Scenario 2: Multi-Variant
```
- Detect object type
- Load appropriate inspection parameters
- Adjust grasp based on object size
- Sort to type-specific bins
```

### Scenario 3: Error Recovery
```
- Detect grasp failure
- Retry grasp (up to 3 times)
- If still failed, report error
- Continue with next object
```

## Key Performance Indicators (KPIs)

Track these metrics:

### Primary KPIs
| Metric | Target | How to Measure |
|--------|--------|----------------|
| Cycle Time | <30s | Time from pick to place |
| Accuracy | >95% | Correct OK/NOK classification |
| Position Error | <1mm | Difference from target |
| Uptime | >90% | Successful operations / total |

### How to Log KPIs

```python
import pandas as pd
from datetime import datetime

# Create KPI logger
class KPILogger:
    def __init__(self):
        self.data = []
    
    def log_cycle(self, cycle_time, accuracy, position_error, success):
        self.data.append({
            'timestamp': datetime.now(),
            'cycle_time': cycle_time,
            'accuracy': accuracy,
            'position_error': position_error,
            'success': success
        })
    
    def get_stats(self):
        df = pd.DataFrame(self.data)
        return df.describe()

# Use it
kpi_logger = KPILogger()
kpi_logger.log_cycle(cycle_time=25.3, accuracy=0.98, 
                     position_error=0.5, success=True)
```

## Code Templates

### Template: State Machine

```python
class RoboticCellStateMachine:
    def __init__(self):
        self.state = 'IDLE'
        self.states = ['IDLE', 'DETECT', 'PICK', 'INSPECT', 
                       'SORT', 'ERROR']
    
    def run(self):
        while True:
            if self.state == 'IDLE':
                self.idle_state()
            elif self.state == 'DETECT':
                self.detect_state()
            elif self.state == 'PICK':
                self.pick_state()
            elif self.state == 'INSPECT':
                self.inspect_state()
            elif self.state == 'SORT':
                self.sort_state()
            elif self.state == 'ERROR':
                self.error_state()
    
    def idle_state(self):
        # Wait for object
        if object_detected():
            self.state = 'DETECT'
    
    # Implement other states...
```

### Template: Vision System

```python
class VisionSystem:
    def __init__(self, camera_matrix, distortion):
        self.K = camera_matrix
        self.dist = distortion
    
    def detect_objects(self, image):
        """Detect objects in image"""
        # Your detection algorithm
        objects = []
        return objects
    
    def get_position(self, object_pixels):
        """Convert pixel coordinates to robot coordinates"""
        # Camera-robot transformation
        pos_robot = self.pixel_to_robot(object_pixels)
        return pos_robot
    
    def inspect_quality(self, object_image):
        """Check if object is OK or NOK"""
        # Your inspection algorithm
        is_ok = True  # or False
        measurements = {}
        return is_ok, measurements
```

## Troubleshooting Guide

### Issue: IK has no solution
**Check:**
- Is target within workspace?
- Are joint limits respected?
- Is orientation achievable?

**Solution:** Adjust target or implement reachability check

### Issue: Slow cycle time
**Check:**
- Are trajectories optimized?
- Is inspection taking too long?
- Are there unnecessary waits?

**Solution:** Profile code, optimize critical paths

### Issue: Low inspection accuracy
**Check:**
- Camera calibration
- Lighting conditions (in simulation)
- Threshold values

**Solution:** Recalibrate, adjust parameters

## Presentation Tips

### Structure (15 minutes)
1. **Problem & Solution** (2 min) - What and why
2. **Technical Approach** (5 min) - How it works
3. **Live Demo** (5 min) - Show it working
4. **Results & Analysis** (2 min) - Performance data
5. **Q&A** (5-10 min) - Answer questions

### Demo Checklist
- [ ] Test demo scenarios beforehand
- [ ] Have backup recordings (in case of technical issues)
- [ ] Show monitoring dashboard
- [ ] Demonstrate error handling
- [ ] Show performance metrics

### Slides Recommendations
- Max 10 slides
- More visuals, less text
- Include system diagram
- Show KPI results
- Add team photo (optional but nice!)

## Resources at Your Fingertips

### During Sessions
- 📖 Session notebooks (with examples)
- 👨‍🏫 Instructor support
- 📚 Documentation and references
- 💻 Code templates and snippets

### Online
- Robotics Toolbox docs
- OpenCV tutorials
- NumPy/Matplotlib references
- Course forum

## Final Checklist

Before final submission, verify:

### Code
- [ ] All code runs without errors
- [ ] Comments and documentation
- [ ] Clean, organized structure
- [ ] Git commits (if using version control)

### Functionality
- [ ] Complete pick-inspect-sort cycle works
- [ ] All scenarios implemented
- [ ] Error handling functional
- [ ] KPIs measured and logged

### Documentation
- [ ] Technical report complete
- [ ] User manual included
- [ ] Code documentation
- [ ] Architecture diagrams

### Presentation
- [ ] Slides prepared
- [ ] Demo tested
- [ ] Backup plan ready
- [ ] Team roles for presentation assigned

## Motivational Note

This project is your opportunity to:
- Apply everything you've learned
- Create something impressive
- Work as a team
- Solve a realistic problem
- Build your portfolio
- Have fun with robotics! 🤖

**Remember:** The goal is learning, not perfection. Make mistakes, learn from them, and improve. Your instructor is here to guide you, not to judge you.

**You've got this!** 💪

---

**Next Step:** Open `SAE_Industry40_Project.ipynb` and start Session 1!

**Questions?** Ask your instructor during sessions.

**Good luck with your Industry 4.0 project! 🚀**
