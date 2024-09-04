# Manager node

Manager Node(s) are computers that handle API load balancing and manage Inferix's services, including Rendering, AI Training/Inference, and Remote PC services.

A manager node consists of two components: Service Controller and Job Controller. The rendering cost calculations based on the PoR algorithm will be sent by the Service Controller to the end users, allowing them to decide whether to submit an order. The Job Controller (c.f.\cref{subsec:rendering_network}) is responsible for dividing rendering jobs into different tasks and assigning them to Worker Nodes for execution. For example, a $$1000$$-frame video rendering job can be divided into $$200$$ tasks, with each task rendering $$5$$ frames. These tasks are pushed into TaskQueue. Available workers that meet the minimum hardware capability requirements, based on the Inferix Bench index (c.f.\cref{subsec:inferix_bench_ibme}), will be randomly assigned to perform the rendering tasks. The rendered results are then aggregated according to the process outlined in\cref{fig:rendering_service}.