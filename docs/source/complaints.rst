.. Kicking page rebuild 2014-10-30 17:00:08

..
    contents:: Table of Contents
   :depth: 2
   :local:

.. _complaint_workflow:

Complaint Workflow
==================

For more detailed information read `Complaints <http://openprocurement.org/en/complaints.html>`_.

Tender Award Complaints
-----------------------

.. graphviz::

    digraph G {
        rankdir=LR;
        {rank=same; mistaken; invalid; resolved; declined; stopped; cancelled;}
        subgraph cluster_complaint {
            label = "complaint";
            pending; accepted; stopping; satisfied;
        }
        satisfied -> resolved;
        edge[style=dashed];
        draft -> {pending,cancelled}; 
        {pending,accepted} -> stopping;
        edge[style=bold];
        pending -> {accepted,invalid};
        stopping -> {stopped,invalid};
        accepted -> {declined,satisfied,stopped};
        {pending;stopping} -> mistaken;
    }

.. toctree::
    :maxdepth: 1

    complaints-award

Roles
-----

:Complainant:
    dashed

:Procuring entity:
    plain

:Reviewer:
    bold

:Chronograph:
    dotted

Statuses
--------

:draft:
    Initial status

    Complainant can submit claim, upload documents, cancel claim, and re-submit it.

:claim:
    Procuring entity can upload documents and answer to claim.

    Complainant can cancel claim.

:answered:
    Complainant can cancel claim, upload documents, accept solution or escalate claim to complaint.

:pending:
    Reviewer can upload documents and review complaint.

    Complainant can cancel claim.

:invalid:
    Terminal status

    Complaint recognized as invalid.

:declined:
    Terminal status

    Complaint recognized as declined.

:resolved:
    Terminal status

    Complaint recognized as resolved.

:cancelled:
    Terminal status

    Complaint cancelled by complainant.
