I would like you to create a research timeline chart using LaTeX, compile it into a PDF, and push it. Here are the details:
• 2024.11 – 2025.1:
• Established the traccc environment.
• 2025.2 – 2025.3:
• Studied traccc code and algorithms (over 70,000 lines).
• Analyzed next steps and reported to the European team.
• Revised the manuscript for YunChen’s paper.
• 2025.4:
• Set up the Nvidia Nsight Systems environment.
• Profiled traccc to identify bottlenecks.
• Created figures for YunChen’s paper.
• 2025.5:
• Analyzed bottlenecks.
• Attempted code modifications and debugging.
• Split the fit kernel, increasing throughput by 10%.
• Assisted YunChen with the VLSICAD submission.
• 2025.6:
• Replaced Kalman gain matrix operations with INT8 MLP.
• Achieved a 186% speedup but observed physics accuracy degradation.
• Reported results to the European team.
• Assisted YunChen with the TJCAS submission.
• Attempted to set up the Nvidia Nsight Compute environment (encountered severe environmental issues).
• 2025.7:
• Prepared slides and English/Chinese scripts for YunChen’s VLSICAD 2025 oral presentation.
• Prepared slides and scripts for the TJCAS oral presentation.
• Successfully established the Nvidia Nsight Compute environment.
• 2025.8:
• Created the poster for TJCAS.
• Created the poster for FastML.
• Attended VLSICAD and TJCAS.
• 2025.9:
• Attended FastML.
• Started planning for the Weak Lensing competition.
• Assisted Edwin with low-level hardware profiling of Token Reduction using Nvidia Nsight Compute.
• Established a basic flow with Flow Optimization to analyze very large profile data.
• (Note: Mark 'Ongoing NCU Profile Flow Optimization' from this point onward).
• 2025.10:
• Put coursework aside to focus entirely on the Weak Lensing competition (solo sprint).
• Ongoing: NCU Profile Flow Optimization.
• 2025.11:
• Continued the Weak Lensing sprint until mid-November.
• Caught up on coursework progress.
• Conducted NCU profiling on traccc.
• Gained a deeper understanding of bottlenecks and identified the potential for batching.
• Ongoing: NCU Profile Flow Optimization.
• 2025.12:
• Completed multi-event batching optimization by mid-month.
• Achieved a 93% speedup with no physics accuracy loss.
• Researched next steps (post-mid-month) and attempted several incorrect approaches.
• Ongoing: NCU Profile Flow Optimization.
• 2026.1:
• Successfully implemented conditional Jacobian matrix aggregation (18% speedup, no degradation).
• Observation: Discovered that due to batching, the find/fit stage shifted from memory-bound to compute-bound.
• Analysis: High FLOPS tasks cannot be migrated to FPGA due to strict FP64 requirements (even FP32 causes accuracy degradation), making FPGA hardware resources unfeasible.
• Future Direction: The thesis direction will focus on remaining on the GPU and addressing register pressure.
• Ongoing: NCU Profile Flow Optimization."
